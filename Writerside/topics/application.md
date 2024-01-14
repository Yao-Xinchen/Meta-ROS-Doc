# Application

This project is designed for two vehicles: **Sentry** and **Engineer**.

## Sentry

Sentry is an automatic vehicle which cannot be controlled by humans.

### Sentry Motor Configuration

**RID**s stands for ROS IDs, which are used in ROS2 interfaces. \
They are designed to be equal to the IDs of the motors (those stored in hardware). \
For more information, please refer to **ID Allocation** in [Motor Controllers](motor_controllers.md).

| RID | Brand | Type  | Mode |     Usage      |  CID  |  FID  |
|:---:|:-----:|:-----:|:----:|:--------------:|:-----:|:-----:|
|  1  |  DJI  | M3508 |  \   | Forward Wheel  | 0x200 | 0x201 |
|  2  |   ~   |   ~   |  \   |   Left Wheel   |   ~   | 0x202 |
|  3  |   ~   |   ~   |  \   | Backward Wheel |   ~   | 0x203 |
|  4  |   ~   |   ~   |  \   |  Right Wheel   |   ~   | 0x204 |
|  5  |   ~   |   ~   |  \   | Friction Wheel | 0x1FF | 0x305 |
|  6  |   ~   | M6020 |  \   |   Gimbal Yaw   | 0x2FF | 0x20A |
|  7  |   ~   |   ~   |  \   |  Gimbal Pitch  |   ~   | 0x20B |

> The `~` means the same as the previous row. \
> The `CID` and `FID` stand for **Control ID** and **Feedback ID** respectively.
>

## Engineer

Engineer is a manual vehicle which can be controlled by humans.
It is used for extracting, carrying and submitting ores.

### Engineer Motor Configuration