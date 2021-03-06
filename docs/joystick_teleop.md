# Joystick Teleop

## Installation

Install the necessary packages with:
````bash
# On Ubunutu PC
sudo apt-get install xboxdrv ros-kinetic-joy ros-kinetic-joystick-drivers ros-kinetic-teleop-twist-joy
````

Install a joystick viewer with:
```bash
sudo apt-get install jstest-gtk
```

Test a joystick with:
```bash
jstest-gtk
jstest --normal /dev/input/js1
```
**Note:** `/dev/input/js1` might have a different name.

## Usage

Launch a [teleop_twist_joy](http://wiki.ros.org/teleop_twist_joy) node with: 
```bash
# On Ubuntu PC
roslaunch teleop_twist_joy teleop.launch joy_dev:=/dev/input/js1 joy_config:=xd3 enable_turbo_button:=1 scale_linear:=1 scale_angular:=1
```
**Note:** `/dev/input/js1` might have a different name.

Launch a TurtleBot3 with:
```bash
# On TurtleBot3
roslaunch turtlebot3_bringup turtlebot3_robot.launch
```

Launch a simulated turtle robot with:
```bash
# On Ubuntu PC
rosrun turtlesim turtlesim_node /turtle1/cmd_vel:=/cmd_vel
```

Launch a TurtleBot3 in Gazebo with:
```bash
# On Ubuntu PC
roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch
```
