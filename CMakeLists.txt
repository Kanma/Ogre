cmake_minimum_required(VERSION 2.6)
project(OGRE)


# Options
if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Choose the type of build, options are: None (CMAKE_CXX_FLAGS or CMAKE_C_FLAGS used) Debug Release RelWithDebInfo MinSizeRel." FORCE)
endif()

if (NOT OGRE_DEPENDENCIES_PATH)
    set(OGRE_DEPENDENCIES_PATH "${OGRE_SOURCE_DIR}/Dependencies" CACHE STRING "Path to the dependencies of Ogre (by default: ${OGRE_SOURCE_DIR}/Dependencies)")
endif()

if (NOT OGRE_FREEIMAGE_PATH)
    set(OGRE_FREEIMAGE_PATH "" CACHE STRING "Path to FreeImage (by default: $OGRE_DEPENDENCIES_PATH/FreeImage)")
endif()

if (NOT OGRE_FREETYPE_PATH)
    set(OGRE_FREETYPE_PATH "" CACHE STRING "Path to FreeType (by default: $OGRE_DEPENDENCIES_PATH}/freetype)")
endif()

if (NOT OGRE_ZLIB_PATH)
    set(OGRE_ZLIB_PATH "" CACHE STRING "Path to ZLib (by default: $OGRE_DEPENDENCIES_PATH/zlib)")
endif()

if (NOT OGRE_ZZIPLIB_PATH)
    set(OGRE_ZZIPLIB_PATH "" CACHE STRING "Path to zziplib (by default: $OGRE_DEPENDENCIES_PATH/zziplib)")
endif()

if (NOT OGRE_CG_PATH)
    set(OGRE_CG_PATH "" CACHE STRING "Path to Cg (by default: $OGRE_DEPENDENCIES_PATH/Cg)")
endif()


# Set the output path
if (NOT ATHENA_BINARY_DIR)
    set(ATHENA_BINARY_DIR "${OGRE_BINARY_DIR}")
    set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${OGRE_BINARY_DIR}/bin")
    set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${OGRE_BINARY_DIR}/lib")
    set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${OGRE_BINARY_DIR}/bin")
endif()


# Subdirectories to process
# add_subdirectory(OgreMain)

if (OGRE_DEPENDENCIES_PATH STREQUAL "${OGRE_SOURCE_DIR}/Dependencies")
    add_subdirectory(Dependencies)
endif()
