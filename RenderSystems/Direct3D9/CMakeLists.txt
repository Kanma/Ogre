set (HEADER_FILES
  include/OgreD3D9Device.h
  include/OgreD3D9DeviceManager.h
  include/OgreD3D9Driver.h
  include/OgreD3D9DriverList.h
  include/OgreD3D9GpuProgram.h
  include/OgreD3D9GpuProgramManager.h
  include/OgreD3D9HardwareBufferManager.h
  include/OgreD3D9HardwareIndexBuffer.h
  include/OgreD3D9HardwareOcclusionQuery.h
  include/OgreD3D9HardwarePixelBuffer.h
  include/OgreD3D9HardwareVertexBuffer.h
  include/OgreD3D9HLSLProgram.h
  include/OgreD3D9HLSLProgramFactory.h
  include/OgreD3D9Mappings.h
  include/OgreD3D9MultiRenderTarget.h
  include/OgreD3D9Plugin.h
  include/OgreD3D9Prerequisites.h
  include/OgreD3D9RenderSystem.h
  include/OgreD3D9RenderWindow.h
  include/OgreD3D9Resource.h
  include/OgreD3D9ResourceManager.h
  include/OgreD3D9Texture.h
  include/OgreD3D9TextureManager.h
  include/OgreD3D9VertexDeclaration.h
  include/OgreD3D9VideoMode.h
  include/OgreD3D9VideoModeList.h
)

set (SOURCE_FILES
  src/OgreD3D9Device.cpp
  src/OgreD3D9DeviceManager.cpp
  src/OgreD3D9Driver.cpp
  src/OgreD3D9DriverList.cpp
  src/OgreD3D9EngineDll.cpp
  src/OgreD3D9GpuProgram.cpp
  src/OgreD3D9GpuProgramManager.cpp
  src/OgreD3D9HardwareBufferManager.cpp
  src/OgreD3D9HardwareIndexBuffer.cpp
  src/OgreD3D9HardwareOcclusionQuery.cpp
  src/OgreD3D9HardwarePixelBuffer.cpp
  src/OgreD3D9HardwareVertexBuffer.cpp
  src/OgreD3D9HLSLProgram.cpp
  src/OgreD3D9HLSLProgramFactory.cpp
  src/OgreD3D9Mappings.cpp
  src/OgreD3D9MultiRenderTarget.cpp
  src/OgreD3D9Plugin.cpp
  src/OgreD3D9RenderSystem.cpp
  src/OgreD3D9RenderWindow.cpp
  src/OgreD3D9Resource.cpp
  src/OgreD3D9ResourceManager.cpp
  src/OgreD3D9Texture.cpp
  src/OgreD3D9TextureManager.cpp
  src/OgreD3D9VertexDeclaration.cpp
  src/OgreD3D9VideoMode.cpp
  src/OgreD3D9VideoModeList.cpp
)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include
                    ${OGRE_SOURCE_DIR}/include/Ogre
                    ${XMAKE_BINARY_DIR}/include/Ogre
                    ${DirectX_INCLUDE_DIR})

link_directories(${DirectX_LIBRARY_DIR})
add_definitions(-D_USRDLL)


xmake_create_dynamic_library(RENDERSYSTEM_DIRECT3D9 RenderSystem_Direct3D9 ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES})

xmake_project_link(RENDERSYSTEM_DIRECT3D9 OGRE)
target_link_libraries(RenderSystem_Direct3D9 ${DirectX_LIBRARIES})

xmake_add_to_list_property(RENDERSYSTEM_DIRECT3D9 COMPILE_DEFINITIONS "OGRED3DENGINEDLL_EXPORTS")
