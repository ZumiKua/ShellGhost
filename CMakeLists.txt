cmake_minimum_required(VERSION 3.8)
project(ShellGhost)

set(CMAKE_C_STANDARD 99)

set(SOURCE_FILES src/library.c include/library.h)
add_library(ShellGhost ${SOURCE_FILES})
target_include_directories(ShellGhost PUBLIC ${PROJECT_SOURCE_DIR}/include)


add_executable(ShellGhostSample sample/basic.c)
target_include_directories(ShellGhostSample PRIVATE ${PROJECT_SOURCE_DIR}/include)
target_link_libraries(ShellGhostSample ${PROJECT_BINARY_DIR}/libShellGhost.a)