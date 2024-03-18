# cmake_minimum_required(VERSION 2.8)
# project(ch6)

# set(CMAKE_BUILD_TYPE Release)
# set(CMAKE_CXX_FLAGS "-std=c++14 -O3")

# list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/ch6/cmake)

# OpenCV
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

# Ceres
find_package(Ceres REQUIRED)
include_directories(${CERES_INCLUDE_DIRS})

# g2o
find_package(g2o REQUIRED)
include_directories(${g2o_INCLUDE_DIRS})

# Eigen
include_directories(${Eigen_INCLUDE_DIRS})

add_executable(gaussNewton gaussNewton.cpp)
target_link_libraries(gaussNewton ${OpenCV_LIBS} Eigen3::Eigen)

add_executable(ceresCurveFitting ceresCurveFitting.cpp)
target_link_libraries(ceresCurveFitting ${OpenCV_LIBS} ${CERES_LIBRARIES})

add_executable(g2oCurveFitting g2oCurveFitting.cpp)
target_link_libraries(g2oCurveFitting ${OpenCV_LIBS} g2o::core g2o::stuff Eigen3::Eigen)
