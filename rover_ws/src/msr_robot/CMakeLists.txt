cmake_minimum_required(VERSION 3.10)
project(msr_robot)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(xacro REQUIRED)
find_package(robot_state_publisher REQUIRED)
find_package(controller_manager REQUIRED)
find_package(rviz2 REQUIRED)
find_package(rviz_common REQUIRED)
find_package(moveit_ros_move_group REQUIRED)
find_package(moveit_kinematics REQUIRED)
find_package(moveit_planners REQUIRED)
find_package(moveit_simple_controller_manager REQUIRED)
find_package(tf2_ros REQUIRED)
find_package(moveit_ros_visualization REQUIRED)
find_package(moveit_ros_warehouse REQUIRED)
find_package(moveit_setup_assistant REQUIRED)
find_package(rviz_default_plugins REQUIRED)

install(DIRECTORY 
  urdf
  launch
  rviz
  config
  robots
  meshes
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
