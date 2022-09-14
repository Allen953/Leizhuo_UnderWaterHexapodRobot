cmake_minimum_required(VERSION 2.8.3)

project(Leizhuo_UnderWaterHexapodRobot)

find_package(catkin REQUIRED)

find_package(roslaunch)

find_package(catkin REQUIRED COMPONENTS
  message_generation
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

add_message_files(
  FILES
  joint.msg
)

# 生成消息时依赖于 std_msgs
generate_messages(
  DEPENDENCIES
  std_msgs
)
#执行时依赖
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES demo02_talker_listener
  CATKIN_DEPENDS roscpp rospy std_msgs message_runtime
#  DEPENDS system_lib
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

add_executable(Leizhuo_UnderWaterHexapodRobot_FluctuateStepHor src/Leizhuo_UnderWaterHexapodRobot_FluctuateStepHor.cpp)
target_link_libraries(Leizhuo_UnderWaterHexapodRobot_FluctuateStepHor ${catkin_LIBRARIES} ${orocos_kdl_LIBRARIES})

foreach(dir config launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)
