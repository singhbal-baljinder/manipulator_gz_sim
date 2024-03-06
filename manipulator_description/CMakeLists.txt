cmake_minimum_required(VERSION 3.5)
project(manipulator_description)

find_package(ament_cmake REQUIRED)

install(
  DIRECTORY models/r6bot/meshes models/r6bot/srdf models/r6bot/urdf models/r6bot/rviz
  DESTINATION share/${PROJECT_NAME}/models/r6bot
)

ament_environment_hooks("${CMAKE_CURRENT_SOURCE_DIR}/hooks/${PROJECT_NAME}.dsv.in")
ament_environment_hooks("${CMAKE_CURRENT_SOURCE_DIR}/hooks/${PROJECT_NAME}.sh.in")

ament_package()
