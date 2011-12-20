set(SRCS src/main.cpp
         src/OgreXMLMeshSerializer.cpp
         src/OgreXMLSkeletonSerializer.cpp
         src/tinystr.cpp
         src/tinyxml.cpp
         src/tinyxmlerror.cpp
         src/tinyxmlparser.cpp
)

xmake_import_search_paths(OGRE)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include
                    ${OGRE_SOURCE_DIR}/include/Ogre)

add_definitions(-DTIXML_USE_STL)

xmake_create_executable(OGRE_XML_CONVERTER OgreXMLConverter ${SRCS})
xmake_project_link(OGRE_XML_CONVERTER OGRE)
