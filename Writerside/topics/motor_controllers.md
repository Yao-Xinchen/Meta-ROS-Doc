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

## CAN Driver

All motors, except for GO M8010, use CAN bus to communicate with the computer.

They all share the same `CAN Driver`.
The driver is located in `<workspace>/src/<package>/include/<package>/can_driver.hpp`.
It can be used to send and receive CAN frame.

`can_driver.hpp` in different packages are the same.