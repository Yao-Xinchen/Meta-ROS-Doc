# Serial Driver

**Serial driver** is a package that provides a serial port driver for ROS2.

It is used in the **remote_control** package to communicate with the **referee system**. \
It is also used by [Meta-Vision-SolaisNG](https://github.com/Meta-Team/Meta-Vision-SolaisNG)
to communicate with our embedded system [Meta-Embedded](https://github.com/Meta-Team/Meta-Embedded).

> This has not been fully tested yet, by Mar 8th, 2024.
> 
{style="warning"}

## Installation

To install the serial driver, run the following command:

```bash
sudo apt install ros-<distro>-serial-driver
```

## Usage

The usage of the serial driver in `remote_control` is heavily inspired by
the `solais_serial/src/solais_serial_legacy.cpp`
and `solais_serial/include/solais_serial/solais_serial_legacy.hpp`
in [Meta-Vision-SolaisNG](https://github.com/Meta-Team/Meta-Vision-SolaisNG).