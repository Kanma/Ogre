set (HEADER_FILES
  include/OgreCgFxScriptLoader.h
  include/OgreCgPlugin.h
  include/OgreCgPrerequisites.h
  include/OgreCgProgram.h
  include/OgreCgProgramFactory.h
)

set (SOURCE_FILES
  src/OgreCgFxScriptLoader.cpp
  src/OgreCgPlugin.cpp
  src/OgreCgProgram.cpp
  src/OgreCgProgramFactory.cpp
  src/OgreCgProgramManagerDll.cpp
)

include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${OGRE_CG_PATH}/include
    ${OGRE_SOURCE_DIR}/include/Ogre
    ${ATHENA_BINARY_DIR}/include/Ogre
)

if (APPLE)
    include_directories(${OGRE_SOURCE_DIR}/include/Ogre/OSX)
endif()

add_definitions(-D_USRDLL)

if (APPLE)
    add_custom_command(OUTPUT Cg.framework
                       COMMAND rm ARGS "-rf" ${OGRE_BINARY_DIR}/bin/Cg.framework
                       COMMAND cp ARGS "-R" ${OGRE_CG_PATH}/Cg.framework ${OGRE_BINARY_DIR}/bin/Cg.framework
                       COMMENT "Copying Cg.framework...")
endif()


if (APPLE)
    add_library(Plugin_CgProgramManager SHARED ${HEADER_FILES} ${SOURCE_FILES} Cg.framework)
else()
    add_library(Plugin_CgProgramManager SHARED ${HEADER_FILES} ${SOURCE_FILES})
endif()

if (APPLE)
    set_target_properties(Plugin_CgProgramManager PROPERTIES LINK_FLAGS "-F${OGRE_CG_PATH} -Wl,-rpath,@loader_path/.")
    target_link_libraries(Plugin_CgProgramManager OgreMain "-framework Cg")
else()
    set_target_properties(Plugin_CgProgramManager PROPERTIES LINK_FLAGS "-L${OGRE_CG_PATH}/lib")
    target_link_libraries(Plugin_CgProgramManager OgreMain cg)
    configure_file(${OGRE_CG_PATH}/bin/cg.dll ${OGRE_BINARY_DIR}/bin/cg.dll COPYONLY)
endif()
    
set_target_properties(Plugin_CgProgramManager PROPERTIES COMPILE_DEFINITIONS OGRE_CGPLUGIN_EXPORTS)

# Disable "lib" prefix on Unix
if (CMAKE_COMPILER_IS_GNUCXX)
  set_target_properties(Plugin_CgProgramManager PROPERTIES PREFIX "")
endif (CMAKE_COMPILER_IS_GNUCXX)	
