# Development

To develop this project, you need to be capable of multiple skills.
This includes several languages, basic usage of Linux, and familiarity with ROS2.

For more information, please refer to [Prerequisites](prerequisites.md).

## System

This project is mainly developed on **Ubuntu**.
To develop, you need to use a computer with Ubuntu, such as Orin Nano.

Alternatively, you can use a virtual machine on Windows, such as **WSL**.
After editing, you can copy the code to Orin Nano and run it there.

For more information, please refer to [WSL](wsl.md).

## Editor

It's recommended to use VSCode as the editor.

To install, visit [VSCode](https://code.visualstudio.com/#alt-downloads).

> If you are using Orin Nano, be aware it's an ARM64 platform.
> Make sure you download the correct version.
>
{style="note"}

### Extensions

Here are some extensions you may need:

| Extension  | Provider  |                     Description                      |
|:----------:|:---------:|:----------------------------------------------------:|
| **C/C++**  | Microsoft |              C and C++ language support              |
| **Python** | Microsoft |               Python language support                |
|  **ROS**   | Microsoft | support for Robot Operating System (ROS) development |
| **CMake**  |   twxs    |            support for CMake build system            |
| **Clangd** |   LLVM    |         Clangd language server for C and C++         |