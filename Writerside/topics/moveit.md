# Moveit2

**Moveit2** is a set of software tools for motion planning, kinematics, control and navigation.
It is built on top of the Robot Operating System (ROS) and is intended to be used with ROS2.

In this project, it is used to control the robot arm of the robot **Enigneer**.

## Installation

To install **Moveit2**, you need to install ROS2 first.
For more information, refer to [ROS2](ros.md).

After installing ROS2, you can install **Moveit2** with the following command:

```bash
sudo apt install ros-humble-moveit
```

This would install the main package of **Moveit2**.

### Moveit Servo

**Moveit Servo** is a package that provides real-time control of the robot arm.

To install **Moveit Servo**, run the following command:

```bash
sudo apt install ros-humble-moveit-servo
```

## Usage

Moveit2 is used in **scara_moveit2** package.

For more information, refer to [scara_moveit2](scara_moveit.md).