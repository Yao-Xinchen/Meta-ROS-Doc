# Dependencies

ROS2 should be used in **Linux**. We have been using **Ubuntu**.
Other distributions may also work, but we don't guarantee that.

To run the ROS2 program, here are several libraries required.

## ROS2

Official website: [ROS2](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)

ROS2 is the main platform we are using.

On ubuntu 20.04, the **recommended version** is ROS2 **Humble**.
This is not the latest version, but it is the most stable one on our platform.
If you are using other versions, such as Humble, you may need to install ROS by compiling from source.

Further information: [ROS2](ros.md)

## Serial Ports

We are using the **serial** ports to communicate with motor_controllers, referee system and other devices.

For more information, refer to [Serial Ports](serial_ports.md).

### Serial Driver

**Serial driver** is a package that provides a serial port driver for ROS2.

To install the serial driver, run the following command:

```bash
sudo apt install ros-humble-serial-driver
```

## Moveit2

Official website: [Moveit2](https://moveit.ros.org/)

```Bash
sudo apt install ros-humble-moveit
sudo apt install ros-humble-moveit-servo
```

For more information, refer to [Moveit2](moveit.md).

## Vision

There are several packages related to vision.

### Camera Info Manager

```Bash
sudo apt install ros-humble-camera-info-manager
```

> If it still cannot be found during the compilation,
> add `find_package(camera_info_manager REQUIRED)` to the `rm_vision_ros2_mindvision_camera/CMakeLists.txt`.
>

## CAN Bus

Nvidia archive: [CAN](https://docs.nvidia.com/jetson/archives/r35.3.1/DeveloperGuide/text/HR/ControllerAreaNetworkCan.html)

To enable CAN bus, run the following commands:

```bash
sudo busybox devmem 0x0c303018 w 0xc458
sudo busybox devmem 0x0c303010 w 0xc400
sudo modprobe can
sudo modprobe can_raw
sudo modprobe mttcan
ip link set can0 up type can bitrate 1000000 dbitrate 1000000 berr-reporting on fd on
```

> These commands must be executed on each boot.
>
{style="note"}

> The bitrate is set to 1M, which is the default one of DJI motors.
> If you want to change it, you need to change the value in the command.

> For convenience, it's better to add these commands to the startup script.

For more information, refer to [CAN Bus](can_bus.md).