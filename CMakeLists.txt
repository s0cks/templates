cmake_minimum_required(VERSION 3.7)
project("%PROJECT_NAME%" CXX)

set(CMAKE_CXX_STANDARD 11)

file(GLOB_RECURSE PROJECT_SOURCES Sources/*.cc Sources/*.h)
list(REMOVE_ITEM PROJECT_SOURCES "main.cc")

add_library("lib${PROJECT_NAME}" STATIC ${PROJECT_SOURCES})
add_executable("${PROJECT_NAME}" "Sources/main.cc")
target_link_libraries("${PROJECT_NAME}" "lib${PROJECT_NAME}")
