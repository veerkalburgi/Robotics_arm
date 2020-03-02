# Robotics_arm
This repository is dedicated to robotics arm simulation to perform some specific tasks such as pick and place.
To start the robotics arm simulation launch robotics_arm in Gazebo using the folllowing:

$ roslaunch Robotcs_arm robotic_arm_gazebo.launch

Start Controller 

$ roslauch Robotics_arm roboticd_arm_control.launch

This command will move the top link of the arm to a 1.57 -radian (90-degree)
position, relative to the middle link:

$ rostopic pub -1 /rrbot/joint_mid_top_position_controller/command
std_msgs/Float64 "data: 1.57"

To open the gripper, two commands can be sent consecutively to move the right
gripper and then the left gripper -0.5 radians from its center position:

$ rostopic pub -1
/rrbot/right_gripper_joint_position_controller/command
std_msgs/Float64 "data: -0.5"; rostopic pub -1
/rrbot/left_gripper_joint_position_controller/command
std_msgs/Float64 "data: -0.5"
