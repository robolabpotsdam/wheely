cmake_minimum_required(VERSION 3.0.2)
project(thunderborg)

find_package(catkin REQUIRED COMPONENTS
  nav_msgs
  roscpp
  rospy
  std_msgs
)

include_directories(include ${catkin_INCLUDE_DIRS})

catkin_python_setup()
catkin_package()

add_executable(thunderborg_teleop nodes/thunderborg_teleop.cpp)
target_link_libraries(thunderborg_teleop ${catkin_LIBRARIES})

install(TARGETS thunderborg_teleop
	RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

