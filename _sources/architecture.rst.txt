Package Architecture
====================


We give a short overview of 

* the pattern components, 
* the launch scripts,
* and the packages of ROS2swarm.


Pattern Components 
------------------

A pattern consists of the behavior implementation itself, as well as configuration and launch files. 

+------------------------------------------------+-----------------------------------------------+
| File                                           | Function                                      |
+================================================+===============================================+
| ros2swarm/pattern_domain/pattern_type/         | The behavior logic of the pattern.            |
| pattern_name.py                                |                                               |
+------------------------------------------------+-----------------------------------------------+
| config/robot_type/pattern_domain/pattern_type/ | The parameter configuration for the pattern.  |
| pattern_name.yaml                              | There is one file for each robot type.        |
+------------------------------------------------+-----------------------------------------------+
| launch/pattern_domain/pattern_type/            | The launch file starting the ROS node with    | 
| pattern_name.launch.py                         | parameters specified in pattern_name.yaml.    |
+------------------------------------------------+-----------------------------------------------+

To add a new pattern, copy the files from any existing pattern, e.g., the drive pattern, and implement the desired behavior. 
Also remember to add the files of the new pattern to the setup.py and to register the main function of the new pattern there. 
The new pattern can be started via the start_*.sh scripts with the name defined in the setup.py.


Launch Scripts
--------------

The provided launch scripts help the user to start ROS2swarm and to execute the desired behaviors. There are several scripts which are chained. In this section we explain their purpose and internal call order. We provide scripts both for starting desired swarm behaviors in simulation and on the real robots. 


Simulation
~~~~~~~~~~

For robot types Thymio, TurtleBot3 Waffle Pi and TurtleBot3 Burger:

* start_simulation.sh - shell script to start up the Gazebo simulator and ROS2swarm 
	* launch_gazebo/launch/create_environment.launch.py - central simulation launch script which calls the other launch scripts 
		* launch_gazebo/launch/start_gazebo.launch.py - start the Gazebo simulator
		* launch_gazebo/launch_gazebo/add_bot_node.py - adds a Gazebo robot node for each robot
		* ros2swarm/launch/bringup_patterns.launch.py - manage the start of the pattern for each robot with its own namespace
			* ros2swarm/hardware_protection_layer.py - hardware protection layer node
			* ros2swarm/pattern_domain/pattern_type/pattern_name.launch.py - launch script for the pattern node
			* robot_state_publisher package - robot_state_publisher node

* scripts/add_robots_to_simulation.sh - shell script to add more robots to simulation
	* launch_gazebo/launch/add_robot.launch.py - allows adding additional robots to a simulation started by the create environment script (see above)
	* launch_gazebo/launch_gazebo/add_bot_node.py - adds a Gazebo robot node for each robot
	* ros2swarm/launch/bringup_patterns.launch.py - manage the start of the pattern for each robot with its own namespace
		* etc. as above

For robot type Jackal UGV:

* start a roscore 
* run the rosbridge: https://github.com/ros2/ros1_bridge
* start the jackal simulation: https://github.com/ROS2swarm/jackal-swarm-simulation
* start_simulation.sh - with robot:=jackal


Real Robots
~~~~~~~~~~~


For robot types TurtleBot3 Waffle Pi and TurtleBot3 Burger:

* start_robot.sh - shell script to start up ROS2swarm on a single robot
	* ros2swarm/bringup_robot.launch.py - central robot launch script which adds the other launch scripts to the launch description
	* ros2swarm/turtlebot3_bringup.launch.py - starts the TurtleBot3 robot nodes and launch files

For robot type Jackal:

* start_robot.sh - shell script to start up ROS2swarm on a single robot with robot:=jackal
	* does not start the jackal counterpart, only provides subscribers and publishers of the behavior pattern 
  
  
Package Structure
-----------------


ROS2swarm consists of three ROS packages:

* ros2swarm
	* The main package containing the behavior patterns and their configuration and launch files.
* launch_gazebo
	* Scripts to start the Gazebo simulation
* communication_interfaces
	* Interfaces for special ROS messages used by the patterns

