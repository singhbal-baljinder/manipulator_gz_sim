# Robotic Manipulator Simulation
A project simulating a Robot Manipulator Arm using [`ros2-control`](https://control.ros.org/master/index.html) and [Gazebo](https://gazebosim.org/home).

## Included packages

* `manipulator_description` - holds the sdf description of the simulated system and any other assets.

* `manipulator_gazebo` - holds gazebo specific code and configurations. Namely this is where systems end up.

* `manipulator_application` - holds ros2 specific code and configurations.

* `manipulator_bringup` - holds launch files and high level utilities.


## Build and Install

The code requires a ROS2 [Humble](https://docs.ros.org/en/humble/index.html) installation and the suggested [Gazebo Fortress](https://gazebosim.org/docs/latest/ros_installation). Currently it supports only installations on Ubuntu 22.04.

1. Install ROS2 [Humble](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html) and [Gazebo Fortress](https://gazebosim.org/docs/latest/ros_installation).

1. Install necessary tools

    ```bash
    sudo apt install python3-vcstool python3-colcon-common-extensions git wget
    ```
1. Clone this repository in the source folder of your workspace, e.g. <ros2_ws/src>.

1. Use [rosdep](https://docs.ros.org/en/humble/Tutorials/Intermediate/Rosdep.html) to install the dependencies. 

    ```bash
    cd ~/ros2_ws
    source /opt/ros/humble/setup.bash
    sudo rosdep init
    rosdep update
    rosdep install --from-paths src --ignore-src -r -i -y --rosdistro humble
    ```

1. Use [colcon](https://colcon.readthedocs.io/en/released/user/quick-start.html) to build. 
    
    ```bash
    cd ~/ros2_ws
    colcon build
    ```


## Usage

1. In **all** the terminals source ROS2 and the workspace

    ```bash
    source /opt/ros/humble/setup.bash
    source ~/ros2_ws/install/setup.sh
    ```

1. Launch the Gazebo model in one terminal:

    ```bash
     ros2 launch manipulator_bringup manipulator_setup.launch.py
    ```

1. Launch the trajectory generator node in another terminal:

    ```bash
     ros2 launch manipulator_bringup manipulator_setup.launch.py
    ```
