# Serial Ports

Serial ports are used to:

1. Receive information from the referee system.
2. Send information to Unitree motors.

## Intro

To check the serial ports, run the following command:

```bash
cd /dev
ls | grep ttyUSB
```

These commands will list all files in `/dev` whose names contain `ttyUSB`. \
In linux, hardware devices are represented as files.
They can be controlled by reading and writing data to the files.

## RS485

RS485 is a serial communication protocol.
In our program, it is used to communicate with the Unitree motors.
For more information, refer to [Motor Controllers](motor_controllers.md).

Its driver is provided by Unitree. \
A **shared library**(aka **shared object**) is provided to communicate with the motors. \
Two library files `libUnitreeMotorSDK_Arm64.so` and `libUnitreeMotorSDK_Linux64.so` are provided.

## UART

UART is another serial communication protocol. \
There is a 2-pin hardware UART port on Orin Nano.

For more information, refer to [Serial Driver](serial_driver.md).
