# Application

This project is designed for two vehicles: **Sentry** and **Engineer**.

## Sentry

Sentry is an automatic vehicle which cannot be controlled by humans.

### Sentry Motor Configuration

The sentry uses Omni Chassis. \
It has 7 motors in total, including 4 wheels, 2 gimbal motors and 1 friction wheel.

**RID**s stands for ROS IDs, which are used in ROS2 interfaces. \
**HID**s stands for Hardware IDs, which are stored in the devices. \
For more information, please refer to **ID Allocation** in [Motor Controllers](motor_controllers.md).

| RID | HID | Brand | Type  | Mode |     Usage      |  CID  |  FID  |
|:---:|:---:|:-----:|:-----:|:----:|:--------------:|:-----:|:-----:|
|  1  |  1  |  DJI  | M3508 |  \   | Forward Wheel  | 0x200 | 0x201 |
|  2  |  2  |   ~   |   ~   |  \   |   Left Wheel   |   ~   | 0x202 |
|  3  |  3  |   ~   |   ~   |  \   | Backward Wheel |   ~   | 0x203 |
|  4  |  4  |   ~   |   ~   |  \   |  Right Wheel   |   ~   | 0x204 |
|  5  |  5  |   ~   |   ~   |  \   | Friction Wheel | 0x1FF | 0x305 |
|  6  |  2  |   ~   | M6020 |  \   |   Gimbal Yaw   |   ~   | 0x206 |
|  7  |  3  |   ~   |   ~   |  \   |  Gimbal Pitch  |   ~   | 0x207 |

> The `~` means the same as the previous row. \
> The `CID` and `FID` stand for **Control ID** and **Feedback ID** respectively.
>

## Engineer

Engineer is a manual vehicle which can be controlled by humans.
It is used for extracting, carrying and submitting ores.

### Engineer Motor Configuration

The engineer uses AGV Chassis. \
It has 8 motors in total, including 4 wheels and 4 directional motors.

**RID**s stands for ROS IDs, which are used in ROS2 interfaces. \
**HID**s stands for Hardware IDs, which are stored in the devices. \
For more information, please refer to **ID Allocation** in [Motor Controllers](motor_controllers.md).

| RID | HID | Brand | Type  | Mode | Usage  |  CID  |  FID  |
|:---:|:---:|:-----:|:-----:|:----:|:------:|:-----:|:-----:|
|  1  |  1  |  DJI  | M3508 |  \   | LF_Vel | 0x200 | 0x201 |
|  2  |  2  |   ~   |   ~   |  \   | RF_Vel |   ~   | 0x202 |
|  3  |  3  |   ~   |   ~   |  \   | LB_Vel |   ~   | 0x203 |
|  4  |  4  |   ~   |   ~   |  \   | RB_Vel |   ~   | 0x204 |
|  5  |  1  |   ~   | M6020 |  \   | LF_Dir | 0x2FF | 0x205 |
|  6  |  2  |   ~   |   ~   |  \   | RF_Dir |   ~   | 0x206 |
|  7  |  3  |   ~   |   ~   |  \   | LB_Dir |   ~   | 0x207 |
|  8  |  4  |   ~   |   ~   |  \   | RB_Dir |   ~   | 0x208 |

> The `~` means the same as the previous row. \
> The `CID` and `FID` stand for **Control ID** and **Feedback ID** respectively.
>
