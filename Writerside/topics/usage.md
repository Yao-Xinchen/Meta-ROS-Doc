# Usage

## Build

To use this project, you need to build it first.
`colcon` is the compilation tool we are using ROS2.
To build the project, run the following command in the workspace:

```bash
colcon build --cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'
```

In the command, `--cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'` is used to generate the `compile_commands.json` file.
This file is used by the clangd extension to provide code completion and other features.
So, it is not a must to add this argument.

## Run

To run the project, you need to source the setup file first.
The setup file is located in the `install` folder.
To source it, run the following command:

```bash
source install/setup.bash
```
