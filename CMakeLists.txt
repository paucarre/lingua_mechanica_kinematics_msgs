cmake_minimum_required(VERSION 3.10.2)
project(lingua_mechanica_kinematics_msgs)

set(MSG_DEPS
  moveit_msgs
  )

find_package(catkin REQUIRED COMPONENTS message_generation ${MSG_DEPS})

set(MSG_FILES
  RobotStates.msg
)

set(SRV_FILES
  GetPositionIK.srv
)

add_message_files(DIRECTORY msg FILES ${MSG_FILES})
add_service_files(DIRECTORY srv FILES ${SRV_FILES})

generate_messages(DEPENDENCIES ${MSG_DEPS})

catkin_package(CATKIN_DEPENDS message_runtime ${MSG_DEPS})
