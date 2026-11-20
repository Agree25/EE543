# Visual Servoing and Robotics Experiments

A team project exploring **position-based visual servoing (PBVS)** with TurtleBot, ROS, ViSP, and Gazebo, alongside related image-based visual servoing (IBVS) and reinforcement-learning workspaces.

**Project authors:** Vipin Kumar, Yogesh Panjwani, and Kushagra Rathore.

## Repository map

| Path | Contents |
| --- | --- |
| `catkin_ws/src/vs_turtlebot_project/` | TurtleBot visual-servoing package, marker models, simulation setup, and technical report. |
| `new_ws/src/` | Pioneer robot descriptions/control and the visual-servo workspace. |
| `y_ws/src/` | Reinforcement-learning workspace references. |
| `docs/original-setup.md` | Original PBVS, IBVS, and Q-learning setup notes. |

## Starting points

- [TurtleBot project documentation](catkin_ws/src/vs_turtlebot_project/README.md)
- [Simulation setup](catkin_ws/src/vs_turtlebot_project/Simulation_setting.md)
- [Technical report](catkin_ws/src/vs_turtlebot_project/Technical_Report.md)
- [Original setup notes](docs/original-setup.md)

The original environment was **Ubuntu 18.04 with ROS Melodic**, Gazebo, ViSP, and the relevant robot packages. Those historical dependencies are needed to reproduce the experiment; current ROS environments have not been validated.

## Build the TurtleBot package

After installing the dependencies and configuring the marker/world paths described in the linked setup notes:

```sh
cd catkin_ws
source /opt/ros/melodic/setup.bash
catkin_make -DCMAKE_BUILD_TYPE=Release --pkg vs_turtlebot
source devel/setup.bash
roslaunch vs_turtlebot visual-servo-turtlebot-sim.launch_
```

The launch filename ends with an underscore in this repository. Check local world/model paths before launching. Some related workspace entries reference external repositories, so the original notes alone do not guarantee a complete IBVS/RL checkout.

Generated catkin `build/` and `devel/` trees have been removed from version control; they are recreated locally by catkin. The source, robot assets, documentation, and original authorship are preserved. Simulation and hardware behavior have not been revalidated during this cleanup.
