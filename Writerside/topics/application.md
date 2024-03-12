# Application

This project is designed for two vehicles: **Sentry** and **Engineer**.

## Sentry

Sentry is an automatic vehicle which cannot be controlled by humans.
For configuration details, refer to [Sentry](sentry.md).

### Sentry Hardware

The sentry uses Omni Chassis. \
It has 7 motors in total, including 4 wheels, 2 gimbal motors and 1 friction wheel.

### Launch

There are two mainly used launch configs for sentry.

#### auto_sentry.py

This launch file is used for launching the sentry in **automatic** mode.
No manual control is allowed, as required by the competition rules.

#### joy_sentry.py

This launch file is used for launching the sentry in **manual** mode.
A joystick is used for controlling the sentry.
Designed for debugging and testing.

## Engineer

Engineer is a manual vehicle which can be controlled by humans.
It is used for extracting, carrying and submitting ores.
For configuration details, refer to [Engineer](engineer.md).

### Engineer Hardware

The engineer uses AGV Chassis. \
It has 8 motors in total, including 4 wheels and 4 directional motors.
