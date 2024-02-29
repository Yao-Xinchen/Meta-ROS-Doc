# Perception

The **perception** and **execution** layers are the lowest layers in the architecture. \
**perception** is responsible for collecting data from the environment
and providing it to the **decision** layer.

## AHRS Feedback

We use WheelTech N100 AHRS to get the spatial information of the vehicle.
The ROS2 package is `fdilink_ahrs`, which is provided by the manufacturer.
It requires the package `serial` to communicate with the AHRS.

`fdilink_ahrs` is not published officially on GitHub, so it is not included as submodule.
We use the ROS2 version of `serial`, GitHub website: [Serial](https://github.com/jinmenglei/serial_ros2).

## Remote Control

## Teleop Keyboard