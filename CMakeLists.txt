cmake_minimum_required(VERSION 3.0)

project(slambook2 LANGUAGES CXX)

set(CMAKE_BUILD_TYPE "Release")
# 添加c++ 17标准支持
set(CMAKE_CXX_FLAGS "-std=c++17 -O2")

message(STATUS "prefix env path: $ENV{HOME}")

set(CMAKE_PREFIX_PATH "$ENV{HOME}/miniconda3/envs/slambook2")

# Eigen
find_package (Eigen3 REQUIRED)
link_directories(${Eigen_INCLUDE_DIRS})

add_subdirectory(ch3)
add_subdirectory(ch5)
add_subdirectory(ch6)
add_subdirectory(ch7)
