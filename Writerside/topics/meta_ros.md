# Meta-ROS

## Basic Info

[Meta-ROS](https://github.com/Yao-Xinchen/Meta-ROS)

Created by Yao Xinchen, 2023/7/13. \
Based on ROS2 Humble. \
Tested on Nvidia Orin Nano, Ubuntu 20.04. \
Used for RoboMaster Team Meta to control robots.

This project is hoped to be modular, readable and easy to maintain.

This doc can be found at [Meta-ROS-Doc](https://github.com/Yao-Xinchen/Meta-ROS-Doc)

## Dependencies

1. ros-humble
2. serial-driver
3. moveit
4. moveit-servo

For more information, refer to [Dependencies](dependencies.md)

## Structure

4 main layers: Perception -> Decision -> Decomposition -> Execution

For more information, refer to [Layers](layers.md)

## To Compile

First, create a workspace and clone the project.

```Bash
mkdir Meta-ROS
cd Meta-ROS
git clone --recurse-submodules https://github.com/Yao-Xinchen/Meta-ROS src
```

To build run the script `first_build.bash` or `first_build.zsh` with

```Shell
# For bash
bash src/first_build.bash
# For zsh
zsh src/first_build.zsh
```

or run the following commands:

```Bash
colcon build --symlink-install --packages-select serial
source ./install/setup.bash
colcon build --symlink-install --cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'
```

For more information, refer to [Usage](usage.md)
