set (HEADER_FILES
  include/OgreBspLevel.h
  include/OgreBspNode.h
  include/OgreBspPrerequisites.h
  include/OgreBspResourceManager.h
  include/OgreBspSceneManager.h
  include/OgreBspSceneManagerPlugin.h
  include/OgreBspSceneNode.h
  include/OgreQuake3Level.h
  include/OgreQuake3Shader.h
  include/OgreQuake3ShaderManager.h
  include/OgreQuake3Types.h
)

set (SOURCE_FILES
  src/OgreBspLevel.cpp
  src/OgreBspNode.cpp
  src/OgreBspResourceManager.cpp
  src/OgreBspSceneManager.cpp
  src/OgreBspSceneManagerDll.cpp
  src/OgreBspSceneManagerPlugin.cpp
  src/OgreBspSceneNode.cpp
  src/OgreQuake3Level.cpp
  src/OgreQuake3Shader.cpp
  src/OgreQuake3ShaderManager.cpp
)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${OGRE_SOURCE_DIR}/include/Ogre
    ${XMAKE_BINARY_DIR}/include/Ogre
)

if (APPLE)
    include_directories(${OGRE_SOURCE_DIR}/include/Ogre/OSX)
endif()

add_definitions(-D_USRDLL)

xmake_create_dynamic_library(PLUGIN_BSPSCENEMANAGER Plugin_BSPSceneManager ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES})

xmake_project_link(PLUGIN_BSPSCENEMANAGER OGRE)

xmake_add_to_list_property(PLUGIN_BSPSCENEMANAGER COMPILE_DEFINITIONS "OGRE_BSPPLUGIN_EXPORTS")

# Disable "lib" prefix on Unix
set_target_properties(Plugin_BSPSceneManager PROPERTIES PREFIX "")
