set(SRCS main.cpp)

xmake_import_search_paths(OGRE)
include_directories(${OGRE_SOURCE_DIR}/include/Ogre)

xmake_create_executable(OGRE_MESH_UPGRADER OgreMeshUpgrader ${SRCS})
xmake_project_link(OGRE_MESH_UPGRADER OGRE)
