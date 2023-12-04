# Dependence

To run the ROS2 program, here are several libraries required.

## ROS2

Official website: [ROS2](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)

ROS2 is the main platform we are using.

On ubuntu 20.04, the **recommended version** is ROS2 **Foxy**.
This is not the latest version, but it is the most stable one on our platform.
If you are using other versions, such as Humble, you may need to install ROS by compiling from source.

Further information: [ROS-Installation](ros_installation.md)

## Serial-Driver

GitHub website: [Serial Driver](https://github.com/ros-drivers/transport_drivers/tree/humble)

ROS index: [Serial Driver](https://index.ros.org/p/serial_driver/#humble)

To install the serial driver, run the following command:

```bash
sudo apt install ros-<distro>-serial-driver
```

This is a serial driver for ROS2. This is required to communicate with the serial port.

> This only need to be executed once.

## CAN bus

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

For more information, please refer to [CAN Bus](can-bus.md).