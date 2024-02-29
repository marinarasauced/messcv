cmake_minimum_required(VERSION 3.0.2)
project(messcv)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  mess_msgs
  rospy
  sensor_msgs
  std_msgs
)

generate_messages(
  DEPENDENCIES
  geometry_msgs
  mess_msgs
  sensor_msgs
  std_msgs
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
  scripts/onboard/raspicam_stills
  scripts/remote/calibration
  scripts/remote/threat
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

