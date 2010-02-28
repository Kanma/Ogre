if (OGRE_BUILD_PLUGIN_OCTREE)
  add_subdirectory(OctreeSceneManager)
endif (OGRE_BUILD_PLUGIN_OCTREE)

if (OGRE_BUILD_PLUGIN_BSP)
  add_subdirectory(BSPSceneManager)
endif (OGRE_BUILD_PLUGIN_BSP)

if (OGRE_BUILD_PLUGIN_CG)
  add_subdirectory(CgProgramManager)
endif (OGRE_BUILD_PLUGIN_CG)

if (OGRE_BUILD_PLUGIN_PFX)
  add_subdirectory(ParticleFX)
endif (OGRE_BUILD_PLUGIN_PFX)

if (OGRE_BUILD_PLUGIN_PCZ)
  add_subdirectory(PCZSceneManager)
  add_subdirectory(OctreeZone)
endif (OGRE_BUILD_PLUGIN_PCZ)
