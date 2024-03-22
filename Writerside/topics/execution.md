# Execution

The **execution** layer is the lowest layer in the architecture. \
It is responsible for directly controlling the hardware.

## Motor

Motor controllers are used to control the motors. \
They also provide feedback with ROS2 interfaces.

There are three types of motors used in this project. \
They are DJI, DM and Unitree motors.

For more information, refer to [Motor Controllers](motor_controllers.md).

### Interface

All three controllers share the same interfaces. \
They are defined in the package `motor_interface`.

### Configuration

Configuration for motors are written in yaml config files.

Params:
1. int `motor.count`: The number of motors.
2. string[] `motor.rids`: The ROS ID of each motor.
3. int[] `motor.hids`: The hardware ID of each motor.
4. int[] `motor.brands`: The brand of each motor.
5. int[] `motor.types`: The type of each motor.

## Serial Output

This package can be used to output serial data to embedded systems.



## Capacitor