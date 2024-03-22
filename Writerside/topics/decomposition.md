# Decomposition

The **decomposition** layer is responsible for decomposing the high-level tasks into low-level tasks. \
Each package is related to a specific mechanical structure on the robots.

High-level tasks are sent by packages in **decision** layer.
Low-level tasks are sent to the **execution** layer.

## SCARA Moveit

The SCARA robot is used for the arm of the engineer. \
It makes use of **Moveit2** for motion planning.

For more information, refer to [Moveit2](moveit.md).

### Interface

