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
    ${XMAKE_BINARY_DIR}/include/Ogre
)

if (APPLE)
    include_directories(${OGRE_SOURCE_DIR}/include/Ogre/OSX)
endif()

if (WIN32)
    link_directories(${OGRE_CG_PATH}/lib)
endif()

add_definitions(-D_USRDLL)

if (APPLE)
    add_custom_command(OUTPUT Cg.framework
                       COMMAND rm ARGS "-rf" ${XMAKE_BINARY_DIR}/bin/Cg.framework
                       COMMAND cp ARGS "-R" ${OGRE_CG_PATH}/Cg.framework ${XMAKE_BINARY_DIR}/bin/Cg.framework
                       COMMENT "Copying Cg.framework...")
endif()


if (APPLE)
    xmake_create_dynamic_library(PLUGIN_CGPROGRAMMANAGER Plugin_CgProgramManager ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES} Cg.framework)

    # Need to include the frameworks directory in the RPATH for CgProgramManager to be able
    # to find the CG framework
    xmake_add_to_property(PLUGIN_CGPROGRAMMANAGER LINK_FLAGS "-F${OGRE_CG_PATH} -Wl,-rpath,@loader_path/.,-rpath,@loader_path/../Frameworks")
    target_link_libraries(Plugin_CgProgramManager "-framework Cg")
else()
    xmake_create_dynamic_library(PLUGIN_CGPROGRAMMANAGER Plugin_CgProgramManager ${OGRE_VERSION} ${OGRE_VERSION_MAJOR} ${HEADER_FILES} ${SOURCE_FILES})

    if (UNIX)
        xmake_add_to_property(PLUGIN_CGPROGRAMMANAGER LINK_FLAGS "-L${OGRE_CG_PATH}/lib")
        set_target_properties(Plugin_CgProgramManager PROPERTIES INSTALL_RPATH "@loader_rpath/.")
        target_link_libraries(Plugin_CgProgramManager ${Cg_LIBRARIES})
    else()
        target_link_libraries(Plugin_CgProgramManager cg)

        foreach (CONFIG ${CMAKE_CONFIGURATION_TYPES})
            configure_file(${OGRE_CG_PATH}/bin/cg.dll ${XMAKE_BINARY_DIR}/bin/${CONFIG}/cg.dll COPYONLY)
        endforeach()
    endif()
endif()


xmake_project_link(PLUGIN_CGPROGRAMMANAGER OGRE)

xmake_add_to_list_property(PLUGIN_CGPROGRAMMANAGER COMPILE_DEFINITIONS "OGRE_CGPLUGIN_EXPORTS")


# Disable "lib" prefix on Unix
set_target_properties(Plugin_CgProgramManager PROPERTIES PREFIX "")
