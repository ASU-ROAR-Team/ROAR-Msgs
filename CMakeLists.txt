cmake_minimum_required(VERSION 3.0.2)
project(roar_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  roscpp
  rospy
  std_msgs
  geometry_msgs
)

add_message_files(
  FILES
  Landmark.msg
  LandmarkArray.msg
  ModeCommand.msg
  NodeStatus.msg
  RoverStatus.msg
  StateCommand.msg
  EncoderStamped.msg
  Obstacle.msg
  ObstacleArray.msg
  HeartBeat.msg
  IndicatorLight.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  MissionControl.srv
  StartModule.srv
  StopModule.srv
)


add_action_files(
  FILES
  SwitchMode.action
)

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

catkin_package(
  CATKIN_DEPENDS
  message_runtime
  roscpp
  rospy
  std_msgs
  geometry_msgs
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
