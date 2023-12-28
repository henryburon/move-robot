# ME495 Robotics Embedded Systems Homework 3
**Group 3**

Authors: Megan Black, Henry Buron, Damien Koh, Allen Liu, and Kassidy Shedd

## Description
This package is for Part 2 of HW3 from ME495 at Northwestern University.  This package provides an interface to plan and execute robot arm paths using moveit2.  

## Usage Instructions
1. Use `ros2 launch franka_moveit_config moveit.launch.py robot_ip:=dont-care use_fake_hardware:=true` to start the Franka simulation in rviz or `ros2 launch franka_moveit_config moveit.launch.py use_rviz:=false robot_ip:=panda0.robot` to start the Franka in lab
2. Use `ros2 run motion_plan_pkg our_node --ros-args -p goal_x:=0.5 -p goal_y:=-0.5 -p goal_z:=0.2 -p theta:=1.0 -p rotation_axis:=[0.5,0.5,0.0]` to run a test node that demonstrates a simple use case
3. To run the actual arm, run this: `ros2 run motion_plan_pkg our_node --ros-args -p goal_x:=0.5 -p goal_y:=-0.0 -p goal_z:=0.05 -p fake_mode:=False`

## Configuration Instructions

### Methods Offered
The `find_path` method takes in a point and quaternion and determines the path for the arm to follow.

The `angle_axis_to_quaternion` method allows the use to convert a rotation around an axis to a quaternion.

The `read_path` method will return the found path.

The `execute_path` method moves the arm according to the provided path.

The `find_and_execute` method allows for the user to call 1 method to both find the path and move accordingly.

The `find_and_execute_cartesian` method allows user to find and the execute the cartesian path over all waypoints

The `add_box` method adds an object with specified name (string), pose (Pose), and shape (shape_msgs/msg/SolidPrimative) to the planning scene.

The `remove_box` method removes an existing object with specified name (string) from the planning scene.
