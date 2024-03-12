# Meta Vision

This package is the auto-aim system for the robot.
It analyzes the image from the camera and sends the target position to the decision layer.

[Meta-Vision-SolaisNG](https://github.com/Meta-Team/Meta-Vision-SolaisNG/tree/humble) is the upstream repository of this package.
It was used in 2023 Shanghai RMUL and 2023 Shenzhen RMUC.
It was designed to cooperate with the embedded system [Meta-Embedded](https://github.com/Meta-Team/Meta-Embedded) by communicating with the serial port.
A USB-to-Serial(such as CH340) is required to enable the package to function properly.

This package is designed to be used in this complete upper-machine system.
All unnecessary parts related to serial are removed, and replaced with ROS2 interfaces.