cmake_minimum_required(VERSION 3.1)
project(game.libretro.mame2000)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(MAME2000_LIB NAMES mame2000_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(MAME2000_CUSTOM_BINARY ${MAME2000_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} MAME2000 "")

include(CPack)
