cmake_minimum_required(VERSION 2.8.3)
project(squirrel_grasping)

find_package(catkin REQUIRED
  rospy
  squirrel_manipulation_msgs
  squirrel_ptp_server
  actionlib
  actionlib_msgs
  mongodb_store
  tf
  squirrel_softhand
  kclhand_control
  geometry_msgs
  visualization_msgs
)

catkin_python_setup()

catkin_package(
)

install(PROGRAMS
   scripts/squirrel_grasping_node.py
   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
 )

install(FILES
   launch/squirrel_grasping_metahand.launch
   launch/squirrel_grasping_softhand.launch
   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
 )
