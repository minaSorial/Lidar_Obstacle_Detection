### Lidar.

**Repo description** This project deals with filitring segmentation and clustring lidar point to detect and track obstacles around a car .

## Local Installation

### Ubuntu

1. Clone this github repo:

   ```sh
   cd ~
   git clone https://github.com/minaSorial/Lidar_Obstacle_Detection.git
   ```

2. Edit [CMakeLists.txt](CMakeLists.txt) as follows:

```cmake
cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

add_definitions(-std=c++14)

set(CXX_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")

project(playback)

find_package(PCL 1.11 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
list(REMOVE_ITEM PCL_LIBRARIES "vtkproj4")


add_executable (environment src/environment.cpp src/render/render.cpp src/processPointClouds.cpp)
target_link_libraries (environment ${PCL_LIBRARIES})
```

3. Execute the following commands in a terminal

   ```shell
   sudo apt install libpcl-dev
   cd ~/Lidar_Obstacle_Detection
   mkdir build && cd build
   cmake ..
   make
   ./environment
   ```
