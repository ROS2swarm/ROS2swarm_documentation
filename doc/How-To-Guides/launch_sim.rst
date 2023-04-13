Launch Simulation
=================


Launch Scripts
--------------

.. _ start_simulation:
start_simulation.sh
~~~~~~~~~~~~~~~~~~~

We provide Gazebo simulations for ROS2swarm. 
To facilitate starting the simulation and the desired swarm behavior, we provide the launch script ``start_simulation.sh``. 
The launch script launches the simulation environment in Gazebo, the desired number of robots, as well as the selected swarm behavior. 
For this purpose, the launch script ``start_simulation.sh`` offers several parameterization options: 

+---------------+------------------------------------------+-------------------------------------------+
| Parameter     | Options                                  | Description                               |
+===============+==========================================+===========================================+
| gazebo_world  | see `Gazebo Worlds`_                     | simulation environment                    |
+---------------+------------------------------------------+-------------------------------------------+
| pattern       | see `Swarm  Behaviors <patterns>`        | executed swarm behavior                   |
+---------------+------------------------------------------+-------------------------------------------+
| number_robots | int                                      | number of launched robots                 |
+---------------+------------------------------------------+-------------------------------------------+
| log_level     | debug, info                              | ROS log level for development             |
+---------------+------------------------------------------+-------------------------------------------+
| robot         | see `Supported Robot Platforms <robots>` | launched robot type                       | 
+---------------+------------------------------------------+-------------------------------------------+
| x_start       | float                                    | first position on x-axis                  | 
+-------------------------------+----------+-----------------------------------------------------------+
| x_dist        | float                                    | increment along x-axis for robot position | 
+---------------+------------------------------------------+-------------------------------------------+
| y_start       | float                                    | first position on y-axis                  | 
+---------------+------------------------------------------+-------------------------------------------+
| y_dist        | float                                    | increment along y-axis for robot position | 
+---------------+------------------------------------------+-------------------------------------------+

After setting the parameters, you can start your swarm simulation by executing 

..  code-block:: console

	bash start_simulation.sh 

in the terminal. 

The swarm behavior will be executed by the robots after the start command is received.  

..  code-block:: console

	ros2 topic pub --once /swarm_command communication_interfaces/msg/Int8Message "{data: 1}" 

We provide launch script ``start_command.sh`` to facilitate the start of the robots. 

..  code-block:: console

	bash start_command.sh 


add_robots_to_simulation.sh
~~~~~~~~~~~~~~~~~~~~~~~~~~~

More robots of the same type or of a different type can be added to a running simulation using the ``add_robots_to_simulation.sh`` script. 
It offers several parameterization options: 

+---------------+------------------------------------------+-------------------------------------------+
| Parameter     | Options                                  | Description                               |
+===============+==========================================+===========================================+
| start_index   | int                                      | index for first newly added robot         |
+---------------+------------------------------------------+-------------------------------------------+   
| version       | 1, 2                                     | ROS version of robot model                |
+---------------+------------------------------------------+-------------------------------------------+            
| `others`      | see `start_simulation`_                                                              | 
+---------------+------------------------------------------+-------------------------------------------+

 

.. _Gazebo Worlds:
Gazebo worlds
-------------

* arena_large.world 
* arena.world 
* empty.world 
* turtle.world 
* 560x540m.world
* Ymaze.world
* Ymaze_camber.world
* Ymaze_camber_top.world 
