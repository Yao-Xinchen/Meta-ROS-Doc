# Motor Controllers

## Intro

There are motors from different manufacturers used in this project.
Given that their communication protocols are different, we need to use different motor controllers.

A list of the motors we are using is shown below.

| Motor Type | Protocol  |               Usage on vehicles               |
|:----------:|:---------:|:---------------------------------------------:|
|  DJI 3508  | CAN / PWM |  The four wheels on chassis, friction wheel   |
|  DJI 6020  | CAN / PWM | Gimbal yaw, directional motors on AGV chassis |
|  DM J4310  |    CAN    |              The trigger on dart              |
|  GO M8010  |   RS485   |            Joint motors on the arm            |

> PWM has not been used yet.
> 
{style="note"}

## CAN Bus

All motors, except for GO M8010, use CAN bus to communicate with the computer.

### CAN Driver

They all share the same `CAN Driver`. \
The driver is located in `<package>/include/<package>/can_driver.hpp`. \
It is used for basic CAN operations, such as sending and receiving frames. \
`can_driver.hpp` in different packages are the same.

### ID Allocation

The ID of each motor is allocated in the following table.

| Motor Type |  Mode   |  ID   | Control ID | Feedback ID |
|:----------:|:-------:|:-----:|:----------:|:-----------:|
|  DJI 3508  |    \    | 1 ~ 4 |   0x200    | 0x200 + ID  |
|  DJI 3508  |    \    | 5 ~ 8 |   0x1FF    | 0x200 + ID  |
|  DJI 6020  |    \    | 1 ~ 4 |   0x1FF    | 0x204 + ID  |
|  DJI 6020  |    \    | 5 ~ 7 |   0x2FF    | 0x204 + ID  |
|  DM J4310  |   MIT   |  any  |     ID     |    0x300    |
|  DM J4310  | POS_VEL |  any  | 0x100 + ID |    0x300    |
|  DM J4310  |   VEL   |  any  | 0x200 + ID |    0X300    |

> There are intersections between different protocols.
> Make sure there is **no** conflict.
>
{style="warning"}

For more information, please refer to [DJI Motors](dji_motors.md) and [DM Motors](dm_motors.md).

## RS485

RS485 is a serial communication protocol. \
