cmake_minimum_required(VERSION 2.8.3)
project(etna_s3li_playback)

find_package(catkin REQUIRED)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

if(CATKIN_ENABLE_TESTING)
  find_package(rostest REQUIRED)
endif()

catkin_package()

install(
  PROGRAMS 
  scripts/shell1.sh
  scripts/shell2.sh
  scripts/shell3.sh
  scripts/shell4.sh
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

install(DIRECTORY 
  bags 
  config 
  launch
  rviz 
  scripts 
  urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
