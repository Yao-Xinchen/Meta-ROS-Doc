# Usage

## Clone

First choose a directory to store the workspace. \
Then clone the project into the subdirectory `src`:

```bash
mkdir Meta-ROS
cd Meta-ROS
git clone --recurse-submodules https://github.com/Yao-Xinchen/Meta-ROS src
```

## Build

To use this project, you need to build it first.
`colcon` is the compilation tool we are using ROS2.

The first time to build the project, you can run the script `first_build.bash` or `first_build.zsh` with:

```Shell
# For bash
bash src/first_build.bash
# For zsh
zsh src/first_build.zsh
```

or run the following commands:

```Bash
colcon build --symlink-install --packages-select serial
source ./install/setup.bash
colcon build --symlink-install --cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'
```

Later, you can just run the following command to build the project:
```Bash
colcon build --symlink-install --cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'
```

### Explanation

This would generate `build`, `install`, and `log` folders in the workspace.

```Text
.
├── build
├── install
├── log
└── src
```

`--packages-select serial` is used to only build the `serial` package.
This is because the `serial` package is a dependency of the `fdilink_ahrs` package.
It needs to be sourced before building the `fdilink_ahrs` package.

`--symlink-install` is used to create symbolic links to the files in the `install` folder.
This can avoid copying files and save the trouble of recompiling when you modify the config files in source code.

`--cmake-args '-DCMAKE_EXPORT_COMPILE_COMMANDS=On'` is used to generate the `compile_commands.json` file.
This file is used by the `clangd` extension to provide code completion and other features.
For more information, refer to [Development](development.md).

It is stored in the `build` folder.
If `clangd` cannot find it, you can add param to the `clangd` extension: `-compile-commands-dir=${workspaceFolder}/build`

## Run

To run the project, you need to source the setup file first.
The setup file is located in the `install` folder.
To source it, run the following command:

```bash
source install/setup.bash
```

Then, launch nodes with one of the launch file in package `application`.

For more information, refer to [Application](application.md).
