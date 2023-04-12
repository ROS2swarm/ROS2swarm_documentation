Swarm Behaviors
===============

ROS2swarm includes a library of swarm behaviors that are separated into movement patterns for robot motion and voting patterns for collective decision-making. 
Every pattern can either be a basic pattern (i.e., basic building blocks) or a combined pattern (i.e., using one or more patterns to create a more complex behavior). 

The different patterns may have requirements regarding the sensory setup to be executable. 
We summarize the existing patterns as well as their requirements in the following table. 


+-------------------------------+----------+----------+------------+-------+---------------------+
| Pattern                       | Domain   | Type     | Simulation | Robot | Sensor Requirements |
+===============================+==========+==========+============+=======+=====================+
| aggregation                   | Movement | Basic    | x          | x     | LiDAR or IR         |
+-------------------------------+----------+----------+------------+-------+---------------------+
| attraction                    | Movement | Basic    | x          | x     | LiDAR or IR         |
+-------------------------------+----------+----------+------------+-------+---------------------+
| attraction 2                  | Movement | Basic    | x          | x     | LiDAR or IR         |
+-------------------------------+----------+----------+------------+-------+---------------------+
| dispersion                    | Movement | Basic    | x          | x     | LiDAR or IR         |
+-------------------------------+----------+----------+------------+-------+---------------------+
| drive                         | Movement | Basic    | x          | x     |                     |
+-------------------------------+----------+----------+------------+-------+---------------------+
| magnetometer                  | Movement | Basic    | -          | x     |                     |
+-------------------------------+----------+----------+------------+-------+---------------------+
| minimalist flocking           | Movement | Basic    | x          | x     | LiDAR or IR         |
+-------------------------------+----------+----------+------------+-------+---------------------+
| random walk                   | Movement | Basic    | x          | x     |                     |
+-------------------------------+----------+----------+------------+-------+---------------------+
| discussed dispersion pattern  | Movement | Combined | x          | x     | LiDAR or IR         |
+-------------------------------+----------+----------+------------+-------+---------------------+
| voter model                   | Voting   | Basic    | x          | x     |                     |
+-------------------------------+----------+----------+------------+-------+---------------------+
| majority rule                 | Voting   | Basic    | x          | x     |                     |
+-------------------------------+----------+----------+------------+-------+---------------------+
