PBVS Using Turtlebot Project and VISP
A task of visually controlling the movement of a Turtlebot robot, accomplished through the integration of the Robot Operating System (ROS) and the Visual Servoing Platform (VISP).

Author:-
**Vipin Kumar
Yogesh Panjwani
Kushagra Rathore**

Objective:
To implement position based visual servoing in order to control a Turtlebot3 waffle robot.

The package includes a collection of nodes designed for conducting visual servoing demonstrations on a physical Turtlebot3 robot fitted with a camera (specifically the Waffle model). These nodes showcase the application of the vision_visp stack, highlighting the use of the visp_auto_tracker for target tracking and visp for implementing position-based visual servoing.


**Position Based Visual Servoing (PBVS)**

Setting simulation environment HERE:-

In here we will set up the environment of the simulation, which is using Gazebo. The main thing to do is to insert the marker (in this case, we are using qrcode) to the gazebo world.

Download the marker0 folder.

Move the marker0 folder to gazebo environment by following the below steps:

Go to Home directory, press Ctrl + H to show hidden files
Go to .gazebo
Go to models (if no such folder is present then create it)
Paste the marker0 folder
Start the turtlebot in the simulated world using this command:

$ roslaunch turtlebot_gazebo turtlebot_world.launch

Choose Insert in the properties tab, and choose marker0 model

Place the marker in the world

Save the world file (.world) -- We save it as marker_world.world --

Open visual-servo-turtlebot-sim.launch_ and change the directory in line 16

<arg name="world_name" value="[PATH TO YOUR MARKER WORLD]"/>



The target that will be tracked is a QR code. 

Installation

Make sure to use Ubuntu 18.04 as we will be using ROS Melodic.

Note: Using virtual machine is least preferable as it may lag.

Install ROS Melodic from the following link: http://wiki.ros.org/melodic/Installation/Ubuntu.

Now, open the terminal and write the following commands:

mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/src

catkin_init_workspace

cd ~/catkin_ws

catkin_make

Bring the source

cd ~/catkin_ws/src

Get vs_turtlebot stack that does the visual servoing

git clone to_be_added

Install dependencies

source ~/catkin_ws/devel/setup.bash

rosdep update

rosdep install vs_turtlebot

Build the source

cd ~/catkin_ws

catkin_make -DCMAKE_BUILD_TYPE=Release --pkg vs_turtlebot

Usage

Start visual servoing demo on gazebo simulation using:

source ~/catkin_ws/devel/setup.bash

roslaunch vs_turtlebot visual-servo-turtlebot-sim.launch_

The process involves launching a window called "visp_auto_tracker debug display" which displays the camera's input images. When the target (marker) is placed in front of the camera, it is automatically detected, and the robot receives a velocity command to move towards the target.




**IBVS**

Now, open the terminal and write the following commands:

mkdir -p ~/new_ws/src

cd ~/new_ws/src

catkin_init_workspace

cd ~/new_ws

catkin_make

Bring the source

cd ~/new_ws/src

Get vs_turtlebot stack that does the visual servoing

git clone to_be_added

Install dependencies

source ~/catkin_ws/devel/setup.bash


Build the source

cd ~/catkin_ws

catkin_make 

Usage

Start visual servoing demo on gazebo simulation using:

source ~/new_ws/devel/setup.bash

Run gazebo and add the pionner3dx model

roslaunch visual_servo gazebo_pioneer_amcl.launch

Compile and run the visual servo program

cd ~/catkin_ws/src/visual_servo/src/

mkdir -p build

cd build

cmake ..

make

./tutorial-ros-pioneer-visual-servo




**Q Learning in RL**

Now, open the terminal and write the following commands:

mkdir -p ~/y_ws/src

cd ~/y_ws/src

catkin_init_workspace

cd ~/y_ws

catkin_make

Bring the source

cd ~/y_ws/src

Build the source

cd ~/y_ws

catkin_make

source ~/y_ws/devel/setup.bash

export TURTLEBOT3_MODEL=burger

roslaunch turtlebot3_gazebo turtlebot3_world.launch

In New Terminal:

cd ~/y_ws/

source ~/y_ws/devel/setup.bash

rosrun master_rad learning_node.py

Now to run Rwiz:

Simply write rwiz in new terminal


