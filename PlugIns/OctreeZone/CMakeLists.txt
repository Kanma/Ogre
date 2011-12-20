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
    ${XMAKE_BINARY_DIR}/include/Ogre
)

if (APPLE)
    include_directories(${OGRE_SOURCE_DIR}/include/Ogre/OSX)
endif()

add_definitions(-D_USRDLL)


xmake_create_dynamic_library(PLUGIN_OCTREEZONE Plugin_OctreeZone ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES})

xmake_project_link(PLUGIN_OCTREEZONE OGRE PLUGIN_PCZSCENEMANAGER)

xmake_add_to_list_property(PLUGIN_OCTREEZONE COMPILE_DEFINITIONS "OGRE_OCTREEZONEPLUGIN_EXPORTS")


# Need to include the plugins directory in the RPATH for OctreeZone to be able
# to find the PCZSceneManager library
if (APPLE)
    xmake_add_to_property(PLUGIN_OCTREEZONE LINK_FLAGS "-Wl,-rpath,@loader_path/.,-rpath,@loader_path/../Plugins")
elseif (UNIX)
    xmake_add_to_property(PLUGIN_OCTREEZONE INSTALL_RPATH "@loader_path/.")
endif ()


# Disable "lib" prefix on Unix
if (CMAKE_COMPILER_IS_GNUCXX)
  set_target_properties(Plugin_OctreeZone PROPERTIES PREFIX "")
endif (CMAKE_COMPILER_IS_GNUCXX)	
