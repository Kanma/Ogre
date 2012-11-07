if (OGRE_BUILD_RENDERSYSTEM_D3D9 AND DirectX_FOUND)
    add_subdirectory(Direct3D9)
endif ()

if (OGRE_BUILD_RENDERSYSTEM_D3D11 AND DirectX_D3D11_FOUND)
    add_subdirectory(Direct3D11)
endif ()

if (OGRE_BUILD_RENDERSYSTEM_GL AND OPENGL_FOUND)
    add_subdirectory(GL)
endif ()
