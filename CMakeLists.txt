cmake_minimum_required(VERSION 2.6)
project(OGRE)

# Use relative paths
# This is mostly to reduce path size for command-line limits on windows
if(WIN32)
  # This seems to break Xcode projects so definitely don't enable on Apple builds
  set(CMAKE_USE_RELATIVE_PATHS true)
  set(CMAKE_SUPPRESS_REGENERATION true)
endif()


include(CMakeDependentOption)


# Options
if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Choose the type of build, options are: None (CMAKE_CXX_FLAGS or CMAKE_C_FLAGS used) Debug Release RelWithDebInfo MinSizeRel." FORCE)
endif()

if (NOT OGRE_CG_PATH)
    set(OGRE_CG_PATH "" CACHE STRING "Path to Cg (by default: ${OGRE_SOURCE_DIR}/Dependencies/Cg)")
endif()

if (NOT OGRE_BOOST_PATH)
    set(OGRE_BOOST_PATH "" CACHE STRING "Path to Boost (by default: ${OGRE_SOURCE_DIR}/Dependencies/boost)")
endif()

if (NOT OGRE_CONFIG_ALLOCATOR)
    set(OGRE_CONFIG_ALLOCATOR 4 CACHE STRING "Specify the memory allocator to use. Possible values: 1 - Standard allocator, 2 - nedmalloc, 3 - User-provided allocator, 4 - nedmalloc with pooling")
endif()

if (NOT OGRE_CONFIG_CONTAINERS_USE_CUSTOM_ALLOCATOR)
    set(OGRE_CONFIG_CONTAINERS_USE_CUSTOM_ALLOCATOR ON CACHE BOOL "STL containers in Ogre use the custom allocator")
endif()

if (NOT OGRE_CONFIG_STRING_USE_CUSTOM_ALLOCATOR)
    set(OGRE_CONFIG_STRING_USE_CUSTOM_ALLOCATOR OFF CACHE BOOL "Ogre String uses the custom allocator")
endif()

if (NOT OGRE_CONFIG_MEMTRACK_DEBUG)
    set(OGRE_CONFIG_MEMTRACK_DEBUG OFF CACHE BOOL "Enable Ogre's memory tracker in debug mode")
endif()

if (NOT OGRE_CONFIG_MEMTRACK_RELEASE)
    set(OGRE_CONFIG_MEMTRACK_RELEASE OFF CACHE BOOL "Enable Ogre's memory tracker in release mode")
endif()

if (NOT OGRE_CONFIG_NEW_COMPILERS)
    set(OGRE_CONFIG_NEW_COMPILERS ON CACHE BOOL "Use the new script compilers.")
endif()

if (NOT DEFINED ATHENA_DOUBLE_PRECISION)
    set(OGRE_DOUBLE_PRECISION OFF CACHE BOOL "Use double-precision floating point numbers")
else()
    set(OGRE_DOUBLE_PRECISION ATHENA_DOUBLE_PRECISION CACHE INTERNAL "" FORCE)
endif()


# Find the render system dependencies
set(CMAKE_MODULE_PATH "${OGRE_SOURCE_DIR}/CMake")

find_package(OpenGL)
if (WIN32)
	find_package(DirectX)
endif()


# Settings for the render systems
cmake_dependent_option(OGRE_BUILD_RENDERSYSTEM_D3D9 "Build Direct3D9 RenderSystem" TRUE "WIN32;DirectX_FOUND" FALSE)
cmake_dependent_option(OGRE_BUILD_RENDERSYSTEM_D3D10 "Build Direct3D10 RenderSystem [EXPERIMENTAL]" FALSE "WIN32;DirectX_D3D10_FOUND" FALSE)
cmake_dependent_option(OGRE_BUILD_RENDERSYSTEM_D3D11 "Build Direct3D11 RenderSystem [EXPERIMENTAL]" FALSE "WIN32;DirectX_D3D11_FOUND" FALSE)
cmake_dependent_option(OGRE_BUILD_RENDERSYSTEM_GL "Build OpenGL RenderSystem" TRUE "OPENGL_FOUND" FALSE)


# Settings for the plugins
if (NOT DEFINED OGRE_BUILD_PLUGIN_BSP)
    option(OGRE_BUILD_PLUGIN_BSP "Build BSP SceneManager plugin" TRUE)
endif()

if (NOT DEFINED OGRE_BUILD_PLUGIN_OCTREE)
    option(OGRE_BUILD_PLUGIN_OCTREE "Build Octree SceneManager plugin" TRUE)
endif()

if (NOT DEFINED OGRE_BUILD_PLUGIN_PCZ)
    option(OGRE_BUILD_PLUGIN_PCZ "Build PCZ SceneManager plugin" TRUE)
endif()

if (NOT DEFINED OGRE_BUILD_PLUGIN_PFX)
    option(OGRE_BUILD_PLUGIN_PFX "Build ParticleFX plugin" TRUE)
endif()

if (NOT DEFINED OGRE_BUILD_PLUGIN_CG)
    option(OGRE_BUILD_PLUGIN_CG "Build CG plugin" TRUE)
endif()


# Set the output path
if (NOT ATHENA_BINARY_DIR)
    set(ATHENA_BINARY_DIR "${OGRE_BINARY_DIR}")
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${OGRE_BINARY_DIR}/bin")
    set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${OGRE_BINARY_DIR}/lib")
    set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${OGRE_BINARY_DIR}/bin")
endif()


# We only support Intel 32bits builds
if (APPLE)
    set(CMAKE_OSX_ARCHITECTURES "i386" CACHE INTERNAL "" FORCE)
    set(CMAKE_OSX_ARCHITECTURES_DEFAULT "ppc" CACHE INTERNAL "" FORCE)
endif()


# Import XMake
if (EXISTS "${OGRE_SOURCE_DIR}/Dependencies/xmake/XMake.cmake")
    include("${OGRE_SOURCE_DIR}/Dependencies/xmake/XMake.cmake")
endif()


# Process the dependencies
add_subdirectory(Dependencies)


# XMake settings
if (APPLE)
    xmake_init_framework(OGRE)
    xmake_add_link_paths(OGRE "${CMAKE_LIBRARY_OUTPUT_DIRECTORY}")
    xmake_add_link_flags(OGRE "-F${CMAKE_LIBRARY_OUTPUT_DIRECTORY}" "-framework Ogre" "-framework Carbon" "-framework Cocoa")
else()
    xmake_init_dynamic(OGRE)
    xmake_add_link_paths(OGRE "${CMAKE_LIBRARY_OUTPUT_DIRECTORY}")
    xmake_add_link_targets(OGRE Ogre)
endif()

xmake_add_include_paths(OGRE ${OGRE_SOURCE_DIR}/include
                             ${ATHENA_BINARY_DIR}/include
                             ${ATHENA_BINARY_DIR}/include/Ogre)


# Determine system endianess
include(TestBigEndian)
test_big_endian(OGRE_TEST_BIG_ENDIAN)


# Settings
set(OGRE_VERSION_MAJOR 1)
set(OGRE_VERSION_MINOR 7)
set(OGRE_VERSION_PATCH 0)
set(OGRE_VERSION "${OGRE_VERSION_MAJOR}.${OGRE_VERSION_MINOR}.${OGRE_VERSION_PATCH}")

set(OGRE_CONFIG_THREADS OFF)
set(OGRE_THREAD_PROVIDER 0)

set(OGRE_USE_BOOST OFF)

if (OGRE_TEST_BIG_ENDIAN)
    set(OGRE_CONFIG_BIG_ENDIAN ON)
else()
    set(OGRE_CONFIG_LITTLE_ENDIAN ON)
endif()


# Paths to the dependencies
if (NOT OGRE_CG_PATH)
    set(OGRE_CG_PATH "${OGRE_SOURCE_DIR}/Dependencies/Cg")
endif()

if (WIN32)
    set(OGRE_CG_INCLUDE_PATH "${OGRE_CG_PATH}/include")
endif()

if (NOT OGRE_BOOST_PATH)
    set(OGRE_BOOST_PATH "${OGRE_SOURCE_DIR}/Dependencies/boost")
endif()

set(OGRE_BOOST_INCLUDE_PATH "${OGRE_BOOST_PATH}")


# Subdirectories to process
add_subdirectory(OgreMain)
add_subdirectory(PlugIns)
add_subdirectory(RenderSystems)
