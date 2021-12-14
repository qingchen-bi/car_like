## **键盘控制操作指令**

roslaunch bringup racecar_gazebo.launch
rosrun racecar_description servo_commands.py
rosrun racecar_description keyboard_teleop.py

## **使用TEB导航**

sudo apt install ros-melodic-teb-local-planner

运行bringup 功能包的 racecar_gazebo_rviz.launch

运行bringup 功能包的 move_base_fake.launch

## **参考链接**

Teb_local_planner：http://wiki.ros.org/teb_local_planner

Ros_control：http://wiki.ros.org/ros_control

Move_base：http://wiki.ros.org/move_base/ 

## car 相关的文件 去掉了命名空间 修改记录

/home/bqc/catkin_mp_ws/src/ackerman_simulation/racecar_description/scripts/servo_commands.py

/home/bqc/catkin_mp_ws/src/ackerman_simulation/bringup/launch/gazebo/racecar.launch

主要去掉了robot joint state publish 的命名空间、控制器的命名空间 ns

/home/bqc/catkin_mp_ws/src/ackerman_simulation/racecar_description/urdf/racecar.urdf.xacro

/home/bqc/catkin_mp_ws/src/ackerman_simulation/bringup/config/ctrl.yaml

## 增加了livox

在 racecar.urdf.xacro 调用了 livox xacro 文件
结合livox gazebo 仓库的功能包使用
把两个功能包拷贝到工作空间下，编译
然后运行两个launch 文件：
**运行bringup 功能包的 racecar_gazebo_rviz.launch**

**运行bringup 功能包的 move_base_fake.launch**

如果不需要livox，把 racecar.urdf.xacro 调用 livox_to_car.xacro 注释掉
