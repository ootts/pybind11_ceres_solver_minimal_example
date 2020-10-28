cmake_minimum_required(VERSION 2.8.12)
project(cmake_example)


find_package(Ceres REQUIRED)
include_directories(${CERES_INCLUDE_DIRS})

add_subdirectory(pybind11)
pybind11_add_module(cmake_example src/main.cpp)


target_link_libraries(cmake_example PRIVATE  ${CERES_LIBRARIES})
