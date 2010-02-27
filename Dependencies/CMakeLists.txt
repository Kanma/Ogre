if (NOT FREEIMAGE_ZLIB_PATH)
    set(FREEIMAGE_ZLIB_PATH "${OGRE_ZLIB_PATH}")
endif()


if (NOT ZZIPLIB_ZLIB_PATH)
    set(ZZIPLIB_ZLIB_PATH "${OGRE_ZLIB_PATH}")
endif()


# Subdirectories to process
if (OGRE_FREEIMAGE_PATH STREQUAL "${CMAKE_CURRENT_SOURCE_DIR}/FreeImage")
    add_subdirectory(FreeImage)
endif()

if (OGRE_FREETYPE_PATH STREQUAL "${CMAKE_CURRENT_SOURCE_DIR}/freetype")
    add_subdirectory(freetype)
endif()

if (OGRE_ZLIB_PATH STREQUAL "${CMAKE_CURRENT_SOURCE_DIR}/zlib")
    add_subdirectory(zlib)
endif()

if (OGRE_ZZIPLIB_PATH STREQUAL "${CMAKE_CURRENT_SOURCE_DIR}/zziplib")
    add_subdirectory(zziplib)
endif()
