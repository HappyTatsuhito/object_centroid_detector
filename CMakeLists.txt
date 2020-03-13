cmake_minimum_required(VERSION 2.8.3)
project(object_centroid_detector)

find_package(catkin REQUIRED COMPONENTS
  pcl_ros
  roscpp
  sensor_msgs
  geometry_msgs
)

catkin_package(
  INCLUDE_DIRS include
  CATKIN_DEPENDS  geometry_msgs roscpp sensor_msgs object_recognizer
)

include_directories(
/usr/local/include
  ${catkin_INCLUDE_DIRS}
  include/
)
add_executable(object_centroid_detector src/object_centroid_detector.cpp)
#add_executable(realsense_tf_publisher src/realsense_tf_publisher.cpp)
target_link_libraries(object_centroid_detector
  ${catkin_LIBRARIES}
)
#target_link_libraries(realsense_tf_publisher
#  ${catkin_LIBRARIES}
#)
