cmake_minimum_required(VERSION 3.8)
project(opencv_lane_detection)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

set(PROJECT_DEPENDENCIES
    ament_cmake
    urdf
    xacro
    gazebo_ros
    robot_state_publisher)
  
foreach(DEPENDENCY ${PROJECT_DEPENDENCIES})
  find_package(${DEPENDENCY} REQUIRED)
endforeach()



install(DIRECTORY
    urdf 
    launch 
    rviz 
    models
    worlds
    DESTINATION share/${PROJECT_NAME}
)

ament_package()
