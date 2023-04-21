Launch Real Robots
==================

The launch script ``start_robot.sh`` facilitates starting the pattern execution of ROS2swarm on real robots. 
It has to be executed on each robot individually. 

The launch script offers several parameterization options: 

+---------------+--------------------------------------------------+-------------------------------------------+
| Parameter     | Options                                          | Description                               |
+===============+==================================================+===========================================+
| pattern       | see :doc:`Swarm  Behaviors <../patterns>`        | executed swarm behavior                   |
+---------------+--------------------------------------------------+-------------------------------------------+
| log_level     | debug, info                                      | ROS log level for development             |
+---------------+--------------------------------------------------+-------------------------------------------+
| robot         | see :doc:`Supported Robot Platforms <../robots>` | launched robot type                       | 
+---------------+--------------------------------------------------+-------------------------------------------+
| sensor_type   | see :doc:`Sensor Layer <../sensors>`             | sensor type of robot                      |
+---------------+--------------------------------------------------+-------------------------------------------+
| robot_number  | int                                              | unique robot ID                           |
+---------------+--------------------------------------------------+-------------------------------------------+
