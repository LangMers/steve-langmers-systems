cmake_minimum_required(VERSION 3.10)
project(langmersapp C)

set(CMAKE_C_STANDARD 99)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})
add_definitions(${GTK3_CFLAGS_OTHER})

add_executable(langmersapp main.c)
target_link_libraries(langmersapp ${GTK3_LIBRARIES})