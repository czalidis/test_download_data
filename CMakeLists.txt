cmake_minimum_required(VERSION 2.8.3)
project(test_download_data)

find_package(catkin REQUIRED)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES test_download_data
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

if(CATKIN_ENABLE_TESTING)
  catkin_download_test_data(
    ${PROJECT_NAME}_32e.pcap
    http://download.ros.org/data/velodyne/32e.pcap
    DESTINATION ${CATKIN_DEVEL_PREFIX}/${CATKIN_PACKAGE_SHARE_DESTINATION}/tests
    MD5 e41d02aac34f0967c03a5597e1d554a9)

  catkin_download_test_data(
    ${PROJECT_NAME}_test.pgm
    http://download.ros.org/data/maps/test.pgm
    DESTINATION ${CATKIN_DEVEL_PREFIX}/${CATKIN_PACKAGE_SHARE_DESTINATION}/tests
    MD5 91d2d5b306c12a46dcad645a3da3cc12)
endif()
