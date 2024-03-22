# Layers

To better group the packages, we can divide it into layers.

In this project, we have the following layers:

1. [**Execution**](execution.md)
    - _capacitor_controller_
    - dji_controller
    - dm_controller
    - serial_output
    - unitree_controller
2. [**Decomposition**](decomposition.md)
    - agv_chassis
    - _duo_gimbal_
    - _mecanum_chassis_
    - omni_chassis
    - scara_moveit
    - shoot_load
    - uni_gimbal
3. [**Decision**](decision.md)
    - auto_sentry
    - joy_vehicle
    - remote_vehicle
    - teleop_moving
    - teleop_shooting
4. [**Perception**](perception.md)
    - ahrs_feedback
    - capacitor_feedback
    - _dbus_control_
    - _lidar_driver_
    - meta_vision
    - referee_serial
    - teleop_keyboard

> packages in _italics_ are not tested yet.
> 
