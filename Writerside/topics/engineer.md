# Engineer

## Motor Configuration

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