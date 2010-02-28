set (HEADER_FILES
  include/OgreHeightmapTerrainZonePageSource.h
  include/OgreOctreeZone.h
  include/OgreOctreeZoneOctree.h
  include/OgreOctreeZonePlugin.h
  include/OgreOctreeZonePrerequisites.h
  include/OgreTerrainVertexProgram.h
  include/OgreTerrainZone.h
  include/OgreTerrainZonePage.h
  include/OgreTerrainZonePageSource.h
  include/OgreTerrainZonePrerequisites.h
  include/OgreTerrainZoneRenderable.h
)

set (SOURCE_FILES
  src/OgreHeightmapTerrainZonePageSource.cpp
  src/OgreOctreeZone.cpp
  src/OgreOctreeZoneDll.cpp
  src/OgreOctreeZoneOctree.cpp
  src/OgreOctreeZonePlugin.cpp
  src/OgreTerrainVertexProgram.cpp
  src/OgreTerrainZone.cpp
  src/OgreTerrainZonePage.cpp
  src/OgreTerrainZonePageSource.cpp
  src/OgreTerrainZoneRenderable.cpp
)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}/../PCZSceneManager/include
    ${OGRE_SOURCE_DIR}/include/Ogre
    ${ATHENA_BINARY_DIR}/include/Ogre
)

if (APPLE)
    include_directories(${OGRE_SOURCE_DIR}/include/Ogre/OSX)
endif()

add_definitions(-D_USRDLL)

add_library(Plugin_OctreeZone SHARED ${HEADER_FILES} ${SOURCE_FILES})
target_link_libraries(Plugin_OctreeZone OgreMain Plugin_PCZSceneManager)

set_property(TARGET Plugin_OctreeZone PROPERTY COMPILE_DEFINITIONS OGRE_OCTREEZONEPLUGIN_EXPORTS)

# Need to include the plugins directory in the RPATH for OctreeZone to be able
# to find the PCZSceneManager library
if (UNIX)
  set_property(TARGET Plugin_OctreeZone APPEND PROPERTY INSTALL_RPATH "@loader_path/.")
endif ()

# Disable "lib" prefix on Unix
if (CMAKE_COMPILER_IS_GNUCXX)
  set_target_properties(Plugin_OctreeZone PROPERTIES PREFIX "")
endif (CMAKE_COMPILER_IS_GNUCXX)	
