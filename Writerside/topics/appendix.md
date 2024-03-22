# Appendix

## Parameters

All parameters are listed below.

| Name                       | Type   | Description                                             |
|----------------------------|--------|---------------------------------------------------------|
| north_offset               | float  | rad, north against the desired front                    |
| auto_rotate                | float  | rad/s, of the chassis                                   |
| comp_ratio                 | float  | used to compensate the rotation of chassis              |
| serial_path                | string | the path to the serial                                  |
| control.trans_vel          | float  | m/s, translation velocity                               |
| control.rot_vel            | float  | m/s, rotation velocity                                  |
| control.aim_sensitivity    | float  | rad/s, the sensitivity of joystick                      |
| control.deadzone           | float  | the deadzone of joystick                                |
| chassis.wheel_radius       | float  | m, the radius of chassis wheels                         |
| chassis.deceleration_ratio | float  | the deceleration within motors on the wheels            |
| chassis.radius             | float  | m, the distance from wheel to the center of the chassis |