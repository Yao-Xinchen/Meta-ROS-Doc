# Application

This project is designed for two vehicles: **Sentry** and **Engineer**.

## Sentry

Sentry is an automatic vehicle which cannot be controlled by humans.

### Sentry Motor Configuration

The sentry uses Omni Chassis. \
It has 7 motors in total, including 4 wheels, 2 gimbal motors and 1 friction wheel.

**RID**s (string) stands for ROS IDs, which are used in ROS2 interfaces. \
**HID**s (int) stands for Hardware IDs, which are stored in the devices. \
For more information, refer to **ID Allocation** in [Motor Controllers](motor_controllers.md).

|  RID   | HID | Brand | Type  | Mode |        Usage        |  CID  |  FID  |
|:------:|:---:|:-----:|:-----:|:----:|:-------------------:|:-----:|:-----:|
|   F    |  1  |  DJI  | M3508 |  \   |    Forward Wheel    | 0x200 | 0x201 |
|   L    |  2  |   ~   |   ~   |  \   |     Left Wheel      |   ~   | 0x202 |
|   B    |  3  |   ~   |   ~   |  \   |   Backward Wheel    |   ~   | 0x203 |
|   R    |  4  |   ~   |   ~   |  \   |     Right Wheel     |   ~   | 0x204 |
| FRIC_U |  5  |   ~   |   ~   |  \   |  Friction Wheel Up  | 0x1FF | 0x205 |
| FRIC_D |  6  |   ~   |   ~   |  \   | Friction Wheel Down |   ~   | 0x206 |
| FEED_L |  7  |   ~   | M2006 |  \   |  Ammo Feeding Left  |   ~   | 0x207 |
| FEED_R |  8  |   ~   |   ~   |  \   | Ammo Feeding Right  |   ~   | 0x208 |
|  YAW   |  5  |   ~   | M6020 |  \   |     Gimbal Yaw      | 0x2FF | 0x209 |
| PITCH  |  6  |   ~   |   ~   |  \   |    Gimbal Pitch     |   ~   | 0x20A |

> The `~` means the same as the previous row. \
> The `CID` and `FID` stand for **Control ID** and **Feedback ID** respectively.
>

## Engineer

Engineer is a manual vehicle which can be controlled by humans.
It is used for extracting, carrying and submitting ores.

### Engineer Motor Configuration

The engineer uses AGV Chassis. \
It has 8 motors in total, including 4 wheels and 4 directional motors.

**RID**s (string) stands for ROS IDs, which are used in ROS2 interfaces. \
**HID**s (int) stands for Hardware IDs, which are stored in the devices. \
For more information, refer to **ID Allocation** in [Motor Controllers](motor_controllers.md).

| RID  | HID | Brand | Type  | Mode | Usage  |  CID  |  FID  |
|:----:|:---:|:-----:|:-----:|:----:|:------:|:-----:|:-----:|
| LF_V |  1  |  DJI  | M3508 |  \   | LF_Vel | 0x200 | 0x201 |
| RF_V |  2  |   ~   |   ~   |  \   | RF_Vel |   ~   | 0x202 |
| RB_V |  3  |   ~   |   ~   |  \   | RB_Vel |   ~   | 0x203 |
| RB_V |  4  |   ~   |   ~   |  \   | LB_Vel |   ~   | 0x204 |
| LF_D |  1  |   ~   | M6020 |  \   | LF_Dir | 0x2FF | 0x205 |
| RF_D |  2  |   ~   |   ~   |  \   | RF_Dir |   ~   | 0x206 |
| RB_D |  3  |   ~   |   ~   |  \   | RB_Dir |   ~   | 0x207 |
| LB_D |  4  |   ~   |   ~   |  \   | LB_Dir |   ~   | 0x208 |

> The `~` means the same as the previous row. \
> The `CID` and `FID` stand for **Control ID** and **Feedback ID** respectively.
>
