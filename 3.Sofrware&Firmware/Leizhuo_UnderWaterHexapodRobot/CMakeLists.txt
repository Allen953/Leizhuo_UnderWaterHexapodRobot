cmake_minimum_required(VERSION 2.8.3)

project(Leizhuo_UnderWaterHexapodRobot)

find_package(catkin REQUIRED)

catkin_package()

find_package(roslaunch)

find_package(catkin REQUIRED COMPONENTS
  controller_manager
  gazebo_ros
  gazebo_ros_control
  joint_state_publisher
  robot_state_publisher
  roscpp
  rospy
  rviz
  xacro
  kdl_parser
  tf
  sensor_msgs
  std_msgs
  trac_ik_lib
  serial
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
  ${orocos_kdl_INCLUDE_DIRS}
)

add_executable(Leizhuo_UnderWaterHexapodRobot src/Leizhuo_UnderWaterHexapodRobot.cpp)
target_link_libraries(Leizhuo_UnderWaterHexapodRobot ${catkin_LIBRARIES} ${orocos_kdl_LIBRARIES})

add_executable(Leizhuo_UnderWaterHexapodRobotMaoStep src/Leizhuo_UnderWaterHexapodRobotMaoStep.cpp)
target_link_libraries(Leizhuo_UnderWaterHexapodRobotMaoStep ${catkin_LIBRARIES} ${orocos_kdl_LIBRARIES})

add_executable(Leizhuo_UnderWaterHexapodRobot_FluctuateStep src/Leizhuo_UnderWaterHexapodRobot_FluctuateStep.cpp)
target_link_libraries(Leizhuo_UnderWaterHexapodRobot_FluctuateStep ${catkin_LIBRARIES} ${orocos_kdl_LIBRARIES})


foreach(dir config launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)
