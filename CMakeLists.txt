cmake_minimum_required(VERSION 3.8)
project(ros2_tf2)

# Default to C++17
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
endif()

# Find required packages
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(tf2_ros REQUIRED)
find_package(geometry_msgs REQUIRED)

# Create executable
add_executable(tf_broadcaster src/tf_broadcaster.cpp)

# Link dependencies
ament_target_dependencies(
  tf_broadcaster
  rclcpp
  tf2_ros
  geometry_msgs
)

# Install executable
install(TARGETS
  tf_broadcaster
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
