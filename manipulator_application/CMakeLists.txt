cmake_minimum_required(VERSION 3.5)

project(manipulator_application)

find_package(ament_cmake REQUIRED)


find_package(kdl_parser REQUIRED)
find_package(rclcpp REQUIRED)
find_package(trajectory_msgs REQUIRED)
find_package(rclcpp_action REQUIRED)
find_package(control_msgs REQUIRED)

## COMPILE
add_executable(reference_generator src/reference_generator.cpp)

ament_target_dependencies(
    reference_generator 
  PUBLIC
    kdl_parser
    rclcpp
    rclcpp_action
    trajectory_msgs
    control_msgs
)

install(
    TARGETS reference_generator
    RUNTIME DESTINATION lib/manipulator_application
)

ament_package()
