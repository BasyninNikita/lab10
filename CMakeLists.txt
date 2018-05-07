cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)

include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/BasyninNikita/hunter/archive/v0.20.68.1.tar.gz"
    SHA1 "7c875d5488e1ad69ec5d0b46f1d7c3e9d0914a4a"
)

project(demo)

hunter_add_package(print)
find_package(print)

add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo print)

install(TARGETS demo RUNTIME DESTINATION bin)
