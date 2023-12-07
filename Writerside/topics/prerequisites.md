# Prerequisites

## Language

### CPP

This project is mainly written in **C++**.
Although it is possible to use Python or other language in ROS2, it is not recommended.
You need to master C++ basics to develop this project, including classes, templates, etc.

C++ is also used in our embedded code: [Meta-Embedded](https://github.com/Meta-Team/Meta-Embedded)

#### learning resources

There's a recommended tutorial on Bilibili:
[CPP Tutorial](https://www.bilibili.com/video/BV1et411b73Z)

This tutorial is in Chinese. It was recommended by our former team-leader.

> It's sufficient to learn until STL inclusively, which is taught in about the 200^th^ video.
> 
> C++ skills can be practiced in further development.
>

### CMake

CMake is a tool to build C++ projects.

There is a file named `CMakeLists.txt` in each package.
Code inside configures how to build the package,
such as dependencies, executables, install targets, etc.

> No need to learn CMake too much. Basic usage is enough.
> 
{style="note"}

### Python

Python is not used as the main language in this project.
However, it is used in some scripts, such as `setup.py` and `launch.py`.