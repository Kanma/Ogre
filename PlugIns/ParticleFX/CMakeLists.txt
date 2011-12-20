set (HEADER_FILES
  include/OgreAreaEmitter.h
  include/OgreBoxEmitterFactory.h
  include/OgreBoxEmitter.h
  include/OgreColourFaderAffector2.h
  include/OgreColourFaderAffectorFactory2.h
  include/OgreColourFaderAffectorFactory.h
  include/OgreColourFaderAffector.h
  include/OgreColourImageAffectorFactory.h
  include/OgreColourImageAffector.h
  include/OgreColourInterpolatorAffectorFactory.h
  include/OgreColourInterpolatorAffector.h
  include/OgreCylinderEmitterFactory.h
  include/OgreCylinderEmitter.h
  include/OgreDeflectorPlaneAffectorFactory.h
  include/OgreDeflectorPlaneAffector.h
  include/OgreDirectionRandomiserAffectorFactory.h
  include/OgreDirectionRandomiserAffector.h
  include/OgreEllipsoidEmitterFactory.h
  include/OgreEllipsoidEmitter.h
  include/OgreHollowEllipsoidEmitterFactory.h
  include/OgreHollowEllipsoidEmitter.h
  include/OgreLinearForceAffectorFactory.h
  include/OgreLinearForceAffector.h
  include/OgreParticleFXPlugin.h
  include/OgreParticleFXPrerequisites.h
  include/OgrePointEmitterFactory.h
  include/OgrePointEmitter.h
  include/OgreRingEmitterFactory.h
  include/OgreRingEmitter.h
  include/OgreRotationAffectorFactory.h
  include/OgreRotationAffector.h
  include/OgreScaleAffectorFactory.h
  include/OgreScaleAffector.h
)

set (SOURCE_FILES
  src/OgreAreaEmitter.cpp
  src/OgreBoxEmitter.cpp
  src/OgreColourFaderAffector2.cpp
  src/OgreColourFaderAffector.cpp
  src/OgreColourImageAffector.cpp
  src/OgreColourInterpolatorAffector.cpp
  src/OgreCylinderEmitter.cpp
  src/OgreDeflectorPlaneAffector.cpp
  src/OgreDirectionRandomiserAffector.cpp
  src/OgreEllipsoidEmitter.cpp
  src/OgreHollowEllipsoidEmitter.cpp
  src/OgreLinearForceAffector.cpp
  src/OgreParticleFX.cpp
  src/OgreParticleFXPlugin.cpp
  src/OgrePointEmitter.cpp
  src/OgreRingEmitter.cpp
  src/OgreRotationAffector.cpp
  src/OgreScaleAffector.cpp
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


xmake_create_dynamic_library(PLUGIN_PARTICLEFX Plugin_ParticleFX ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES})

xmake_project_link(PLUGIN_PARTICLEFX OGRE)

xmake_add_to_list_property(PLUGIN_PARTICLEFX COMPILE_DEFINITIONS "OGRE_PARTICLEFXPLUGIN_EXPORTS")


# Disable "lib" prefix on Unix
if (CMAKE_COMPILER_IS_GNUCXX)
  set_target_properties(Plugin_ParticleFX PROPERTIES PREFIX "")
endif (CMAKE_COMPILER_IS_GNUCXX)	
