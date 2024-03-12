# Interfaces

This is a list of interfaces used in this project.

## Motor Interface

Used to control the motors and receive feedback.

### MotorGoal.msg

```
string[] motor_id
float64[] goal_vel # rad/s
float64[] goal_pos # rad
```

Only one of `goal_vel` and `goal_pos` should be set, the other should be set to `std::nan("")`.

> Both `vel` and `pos` are not decelerated.

### MotorState.msg

```
string[] motor_id
float64[] present_tor
float64[] present_vel # rad/s
float64[] present_pos # rad
```

An optional interface, make the `ENABLE_PUB` macro false to disable it.

## Behavior Interface

Used to control the behavior of the vehicles.

### Aim.msg

```
float64 yaw   # relative to north, clockwise is positive
float64 pitch # rad, relative to horizon. up is positive
float64 roll  # not used yet
```

### Move.msg

```
float64 vel_x # m/s, forward is positive
float64 vel_y # m/s, left is positive
float64 omega # rad/s, counter-clockwise is positive
```

The reference frame is determined by the mode of the chassis.

1. `chassis` mode: the reference is the chassis itself
2. `absolute` mode: the reference is the ground, there can be a chosen `front` direction (determined by `north offset`).
3. `natural` mode: the reference is the gimbal

### Shoot.msg

```
int16 id # 0 or 1, for two feeding
bool fric_state # on or off
bool feed_state # on or off
```

0 for left, 1 for right.

## Vision Interface

Used to receive the vision data.

### AutoAim.msg

```
float64 yaw   # rad
float64 pitch # rad
```

The `yaw` and `pitch` are in the same reference frame as `euler_angles` produced by the `ahrs_feedback` package,
which has yaw = 0 when facing north, pitch = 0 when facing horizon.

## Operation Interface

Used for manual input.

### RemoteControl.msg

```
int16 mouse_x
int16 mouse_y
int16 mouse_z
bool left_button
bool right_button
bool w
bool a
bool s
bool d
bool shift
bool ctrl
bool q
bool e
bool r
bool f
bool g
bool z
bool x
bool c
bool v
bool b
```

This would be used to communicate through referee system.

### TeleopKey.msg

```
bool w
bool a
bool s
bool d
bool q
bool e
bool i
bool j
bool o
bool p
bool space
```

This would be used when using `ssh`.
