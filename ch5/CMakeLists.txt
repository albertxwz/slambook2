# cmake_minimum_required(VERSION 2.8)

# set(CMAKE_BUILD_TYPE "Release")
# # 添加c++ 17标准支持
# set(CMAKE_CXX_FLAGS "-std=c++17 -O2")

# set(CMAKE_PREFIX_PATH "/home/x/xie77777/miniconda3/envs/slambook2")

# include_directories(${CMAKE_PREFIX_PATH}/include/eigen3)

# 寻找OpenCV库
find_package(OpenCV REQUIRED)
# 添加头文件
include_directories(${OpenCV_INCLUDE_DIRS})

add_subdirectory(imageBasics)
add_subdirectory(stereo)
add_subdirectory(rgbd)
