cmake_minimum_required(VERSION 2.8.3)
project(sarafun_msgs)

find_package(catkin REQUIRED COMPONENTS
						genmsg
						message_generation
						geometry_msgs
						std_msgs
						sensor_msgs
						actionlib_msgs
						moveit_msgs
						)

add_message_files(FILES
						CompleteFeedback.msg
						#   targetPose.msg
						KeyframeMsg.msg
						KeyframeList.msg
						)

add_service_files(FILES
						SetPID.srv
						TrackObjects.srv
						LoadKeyframes.srv
						VisualizeTransform.srv
						SelectDetectionType.srv
						BTGeneration.srv
						GetSensorData.srv
						)

add_action_files(FILES
						KeyframeExtraction.action
						#   CommandedGrasp.action
						#   CommandedPose.action
						GraspEstimation.action
						PositionEstimation.action
						Trigger.action
						LoadKeyframes.action
						InitialKeyframe.action
						GraspKeyframe.action
						PickUpKeyframe.action
						AlignKeyframe.action
						ContactKeyframe.action
						AssembledKeyframe.action
						RetractKeyframe.action
						MoveKeyframe.action
						)

# Generate added messages and services with any dependencies listed here
generate_messages(
						DEPENDENCIES
						actionlib_msgs
						geometry_msgs
						std_msgs
						moveit_msgs
						)

catkin_package(CATKIN_DEPENDS
						message_runtime
						geometry_msgs
						sensor_msgs
						std_msgs
						)
