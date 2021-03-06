# Euclid Teleop 

## Usage

Goto the [Monitor](http://euclid.local/#apps) on the Euclid and enable *teleop*

Run *twist_remapper.py* with: 
```bash
# On Ubunutu PC
rosrun euclid_teleop twist_remapper.py
```

Alternatively, specify the remapping in the *~/catkin_ws/src/turtlebot3/turtlebot3_bringup/launch/turtlebot3_core.launch* file:
```xml
<launch>
  <!-- The remap tag has to come before the affected node tag -->
  <remap from="cmd_vel" to="cmd_vel_mux/input/teleop"/>
  
  <node pkg="rosserial_python" type="serial_node.py" name="turtlebot3_core" output="screen">
    <param name="port" value="/dev/ttyACM0"/>
    <param name="baud" value="115200"/>
  </node>

</launch>
``` 

The **remap** tag details are [here](http://wiki.ros.org/roslaunch/XML/remap).

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
