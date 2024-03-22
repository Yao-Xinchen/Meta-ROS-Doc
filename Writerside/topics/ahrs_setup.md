# AHRS Setup

AHRS (Attitude and Heading Reference System) is a device that provides orientation information.

We use N100 produced by WheelTec. It uses serial communication to send data. \
The official manuals on Baidu: [Baidu Drive](https://pan.baidu.com/s/15pNEbn7CuQhxwougQnHY8Q)

## Modify the Serial Port Name

Each device only needs to be modified once.

There is a software provided along with the manuals. \
Locate it under `1.用户手册/惯导系列模块使用手册/WHEELTEC N系列用户手册.pdf`.

> The one we use is equipped with the CP2102.
> 

![ahrs_serial.png](ahrs_serial.png)

## Alias on Linux

The AHRS device need to be given an alias so that its name can be fixed. \
Run the script `src/perception/ahrs_feedback/fdilink_ahrs/wheeltec_udev.sh`
in [Meta-ROS](https://github.com/Yao-Xinchen/Meta-ROS).