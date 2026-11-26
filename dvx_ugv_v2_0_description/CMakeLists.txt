cmake_minimum_required(VERSION 3.8)
project(dvx_ugv_v2_0_description)

find_package(ament_cmake REQUIRED)

install(DIRECTORY config launch meshes rviz urdf
  DESTINATION share/${PROJECT_NAME})

ament_package()
