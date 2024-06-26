In this project, we see the simulation of a 6DOF robotic arm.

<img width="913" alt="adi_1" src="https://github.com/adityaguptaofficial00/mycobot_trial_adi/assets/172889066/f2dea556-36e1-4cab-8ded-4bbb78603c52">



this robotic arm is known as MyCobot and made by elephant robotics.
Through this project, I wanted to make a robotic arm whose position of each link can be changed by a simple terminal command.
This is just the first step towards building the final project, where I will be working on its motion, without using MoveIt 2 or any other pre-existing ROS2 frameworks.

**How to use it?**

1) Launching the bot in rviz and gazebo:
go to the location of folder where you have downloaded the repo on your system and type in:

ros2 launch mycobot_gazebo mycobot_280_arduino_bringup_classic_gazebo.launch.py

2) Setting the position vector of robotic arm:

   The position vector described here tells the angle by which each arm has been rotated according to the 0 array.
   You can change the position array by passing the command;

   ros2 topic pub -1 /set_joint_trajectory trajectory_msgs/msg/JointTrajectory  "{header: {frame_id: base_link}, joint_names: [link1_to_link2, link2_to_link3, link3_to_link4, link4_to_link5, link5_to_link6, link6_to_link6flange, gripper_controller, gripper_base_to_gripper_left2, gripper_left3_to_gripper_left1, gripper_base_to_gripper_right3, gripper_base_to_gripper_right2, gripper_right3_to_gripper_right1],
    points: [{positions: [-1.345,-1.230,0.264,-0.296,0.389,-1.50,-0.7, -0.7, 0.7, 0.7, 0.7, -0.7]}]}"

   (This is just an example position of the robotic arm)    
   for the gripper to be in open position: let the -0.7 be as is, if yoyu want the gripper closed, replace it by 0.

**Future developments in Porject**
- The current model is being worked upon so as to achieve a state where this arm can sense the position of an object in 3d space and grab the object on its own.
- This can be easily achieved through inverse kinematics where we can find out the roation of each arm required to reach the desired postion
- for the estimation of position of the object, using depth camera might be the solution, this area is still being worked upon.

**This project is Inspired by Automatic addison's blog post, where he gives a brief introduction about working with 6DOF robotic arm**
**Major section of the project has been inspired by theres, so feel free to check out their website**

