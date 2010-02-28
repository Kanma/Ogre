set (HEADER_FILES
  include/OgreHeightmapTerrainPageSource.h
  include/OgreOctree.h
  include/OgreOctreeCamera.h
  include/OgreOctreeNode.h
  include/OgreOctreePlugin.h
  include/OgreOctreeSceneManager.h
  include/OgreOctreeSceneQuery.h
  include/OgreTerrainPage.h
  include/OgreTerrainPageSource.h
  include/OgreTerrainPrerequisites.h
  include/OgreTerrainRenderable.h
  include/OgreTerrainSceneManager.h
  include/OgreTerrainVertexProgram.h
)

set (SOURCE_FILES
  src/OgreHeightmapTerrainPageSource.cpp
  src/OgreOctree.cpp
  src/OgreOctreeCamera.cpp
  src/OgreOctreeNode.cpp
  src/OgreOctreePlugin.cpp
  src/OgreOctreeSceneManager.cpp
  src/OgreOctreeSceneManagerDll.cpp
  src/OgreOctreeSceneQuery.cpp
  src/OgreTerrainPage.cpp
  src/OgreTerrainPageSource.cpp
  src/OgreTerrainRenderable.cpp
  src/OgreTerrainSceneManager.cpp
  src/OgreTerrainVertexProgram.cpp
)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${OGRE_SOURCE_DIR}/include/Ogre
    ${ATHENA_BINARY_DIR}/include/Ogre
)

if (APPLE)
    include_directories(${OGRE_SOURCE_DIR}/include/Ogre/OSX)
endif()

add_definitions(-D_USRDLL)

add_library(Plugin_OctreeSceneManager SHARED ${HEADER_FILES} ${SOURCE_FILES})
target_link_libraries(Plugin_OctreeSceneManager OgreMain)

set_target_properties(Plugin_OctreeSceneManager PROPERTIES COMPILE_DEFINITIONS OGRE_TERRAINPLUGIN_EXPORTS)

# Disable "lib" prefix on Unix
if (CMAKE_COMPILER_IS_GNUCXX)
  set_target_properties(Plugin_OctreeSceneManager PROPERTIES PREFIX "")
endif (CMAKE_COMPILER_IS_GNUCXX)	
