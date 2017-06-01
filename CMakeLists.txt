cmake_minimum_required(VERSION 3.6)
project(bellagio)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_COLOR_MAKEFILE ON)

add_custom_target(install-components)

add_subdirectory(libomxil-bellagio)
#set(SOURCE_FILES main.cpp)
#add_executable(bellagio ${SOURCE_FILES})