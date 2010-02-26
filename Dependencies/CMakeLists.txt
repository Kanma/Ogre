if (NOT FREEIMAGE_ZLIB_PATH)
    if (OGRE_ZLIB_PATH)
        set(FREEIMAGE_ZLIB_PATH OGRE_ZLIB_PATH)
    else()
        set(FREEIMAGE_ZLIB_PATH "${OGRE_DEPENDENCIES_PATH}/zlib")
    endif()
endif()


if (NOT ZZIPLIB_ZLIB_PATH)
    if (OGRE_ZLIB_PATH)
        set(ZZIPLIB_ZLIB_PATH OGRE_ZLIB_PATH)
    else()
        set(ZZIPLIB_ZLIB_PATH "${OGRE_DEPENDENCIES_PATH}/zlib")
    endif()
endif()


# Subdirectories to process
add_subdirectory(FreeImage)
add_subdirectory(freetype)
add_subdirectory(zlib)
add_subdirectory(zziplib)
