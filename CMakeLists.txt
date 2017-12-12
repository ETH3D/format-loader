project(ETH3DFormatLoader)
cmake_minimum_required(VERSION 2.8)

set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake)

# External dependency: Eigen3
find_package(Eigen3 REQUIRED)
include_directories(${EIGEN3_INCLUDE_DIRS})

# Settings.
if(NOT CMAKE_BUILD_TYPE)
  message(STATUS "Build type not specified, using RelWithDebInfo")
  set(CMAKE_BUILD_TYPE RelWithDebInfo)
endif()

add_definitions("-O2 -msse2 -msse3 -std=c++11")
include_directories(
    ./src
)

# Executable.
add_executable(ETH3DFormatLoader
    src/cameras.cc
    src/images.cc
    src/main.cc
)
