cmake_minimum_required(VERSION 3.19)
project(ebview LANGUAGES C)
set(CMAKE_C_STANDARD 11)

find_package(Threads)
find_package(GTK2 REQUIRED)

find_path(LIBEB_INCLUDE_DIR NAMES eh.h PATH_SUFFIES eb)
find_library(LIBEB_LIBRARY NAMES eb)
include(FindPackageHandleStandardArgs)
find_package_handle_standard_args(LIBEB FOUND_VAR LIBEB_FOUND REQUIRED_VARS LIBEB_LIBRARY LIBEB_INCLUDE_DIR)
set(LIBEB_INCLUDE_DIRS ${LIBEB_INCLUDE_DIR})
set(LIBEB_LIBRARIES ${LIBEB_LIBRARY})

add_subdirectory(src)