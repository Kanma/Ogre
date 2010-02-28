set (HEADER_FILES
  include/OgreAntiPortal.h
  include/OgreCapsule.h
  include/OgreDefaultZone.h
  include/OgrePCPlane.h
  include/OgrePCZCamera.h
  include/OgrePCZFrustum.h
  include/OgrePCZLight.h
  include/OgrePCZoneFactory.h
  include/OgrePCZone.h
  include/OgrePCZPlugin.h
  include/OgrePCZPrerequisites.h
  include/OgrePCZSceneManager.h
  include/OgrePCZSceneNode.h
  include/OgrePCZSceneQuery.h
  include/OgrePortal.h
  include/OgrePortalBase.h
  include/OgreSegment.h
)

set (SOURCE_FILES
  src/OgreAntiPortal.cpp
  src/OgreCapsule.cpp
  src/OgreDefaultZone.cpp
  src/OgrePCPlane.cpp
  src/OgrePCZCamera.cpp
  src/OgrePCZFrustum.cpp
  src/OgrePCZLight.cpp
  src/OgrePCZone.cpp
  src/OgrePCZoneFactory.cpp
  src/OgrePCZPlugin.cpp
  src/OgrePCZSceneManager.cpp
  src/OgrePCZSceneManagerDll.cpp
  src/OgrePCZSceneNode.cpp
  src/OgrePCZSceneQuery.cpp
  src/OgrePortal.cpp
  src/OgrePortalBase.cpp
  src/OgreSegment.cpp
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

add_library(Plugin_PCZSceneManager SHARED ${HEADER_FILES} ${SOURCE_FILES})
target_link_libraries(Plugin_PCZSceneManager OgreMain)

set_target_properties(Plugin_PCZSceneManager PROPERTIES COMPILE_DEFINITIONS OGRE_PCZPLUGIN_EXPORTS)

# Disable "lib" prefix on Unix
if (CMAKE_COMPILER_IS_GNUCXX)
  set_target_properties(Plugin_PCZSceneManager PROPERTIES PREFIX "")
endif (CMAKE_COMPILER_IS_GNUCXX)	
