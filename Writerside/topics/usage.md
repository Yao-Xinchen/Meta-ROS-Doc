# Usage

## Clone

First choose a directory to store the workspace.
Then clone the project into the subdirectory `src`:

```bash
mkdir -p Meta-ROS
cd Meta-ROS
git clone https://github.com/Yao-Xinchen/Meta-ROS src
```

## Build

To use this project, you need to build it first.
`colcon` is the compilation tool we are using ROS2.
To build the project, run the following command in the workspace:

```bash
colcon build --cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'
```

This would generate `build`, `install`, and `log` folders in the workspace.

````
.
├── build
├── install
├── log
└── src
````

In the command, `--cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'` is used to generate the `compile_commands.json` file.
This file is used by the `clangd` extension to provide code completion and other features.
For more information, please refer to [Development](development.md).

It is stored in the `build` folder.
If `clangd` cannot find it, you can add param to the `clangd` extension: `-compile-commands-dir=${workspaceFolder}/build`

## Run

To run the project, you need to source the setup file first.
The setup file is located in the `install` folder.
To source it, run the following command:

```bash
source install/setup.bash
```
