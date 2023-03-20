# LD06 Lidar ROS2 driver

This is an attempt to fix and improve the driver provided by LDRobots in their
[website](https://www.ldrobot.com/download/44)
Now are be repaired, and have been tested on ROS2 Humble under ubuntu 22.04

## Installation
    cd <your_ws> 
    git clone -b ros2 https://github.com/linoroot/ldlidar src/ldlidar
    rosdep update && rosdep install --from-path src --ignore-src -y
    colcon build
    source install/setup.bash

## Run the driver

    ros2 launch ldlidar ldlidar.launch.py

Optional Parameters:
* `serial_port` used to override the autodetect and select a specific port.
* `lidar_frame` used to override the default `laser` frame_id.
* `topic_name` used to override the default `scan` topic name.

For example:

    ros2 launch ldlidar ldlidar.launch.py serial_port:=/dev/ttyUSB0


---- Original readme ----

## 编译方法

使用catkin编译，执行如下操作

```sh
catkin_make

```



## 运行方法

```sh
source devel/setup.bash
roslaunch ldlidar LD06.launch 

or

rosrun ldlidar ldlidar 
```

rviz的配置在rviz文件夹下面。



## 测试

代码在ubuntun16.04 kinetic版本下测试，使用rviz可视化。
