# dual arm ros driver

This repository provides our customized UR5e integration with robotiq 3 Finger gripper.  

![real_robot](https://user-images.githubusercontent.com/6389003/141102453-e75c4ded-fe8f-4a26-9d55-d97c1e357f7d.JPG)

Tested on Ubuntu 18.04 with ROS Melodic.

### The features and usage of the dual arm driver are described on the [WIKI](https://github.com/yaesolKim/dual_ur5e/wiki).   


## Simulation: Run gazebo, moveit, Rviz   
```
roslaunch ur_e_gazebo dual_arm.launch
roslaunch dual_arm_moveit_config robot_moveit_planning_execution.launch sim:=true
roslaunch dual_arm_moveit_config moveit_rviz.launch config:=true
```   

## Real robot execution: Bring up grippers and robots, Run moveit and Rviz   
Run the lines below in the respective terminals.
```commandline
roscore
roslaunch robotiq_3f_gripper_control dual_gripper_tcp.launch
roslaunch robotiq_3f_gripper_joint_state_publisher dual_gripper_joint_state_publisher.launch
roslaunch robotiq_3f_gripper_visualization robotiq_gripper_upload.launch

roslaunch ur_robot_driver robot_bringup.launch   
roslaunch robot_moveit_config robot_moveit_planning_execution.launch sim:=false     
roslaunch robot_moveit_config moveit_rviz.launch config:=true   
```

For the seperate control for left/right arm
```commandline
roslaunch ur_robot_driver dual_ur_robotiq_bringup.launch   
roslaunch ur5e_moveit_config ur5e_moveit_planning_execution.launch   
roslaunch ur5e_moveit_config moveit_rviz.launch config:=true  
```
## Contact
All bug reports, feedback, comments, contributions or remarks are welcome.
