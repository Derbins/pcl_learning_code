cmake_minimum_required(VERSION 2.6 FATAL_ERROR)  #最低的cmake版本要求
project(MY_GRAND_PROJECT)
find_package(PCL 1.3 REQUIRED COMPONENTS common io)     #寻找模块路径 本工程只需要common 和 io 两个模块
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
add_executable(pcd_write_test pcd_write.cpp)
target_link_libraries(pcd_write_test ${PCL_LIBRARIES})