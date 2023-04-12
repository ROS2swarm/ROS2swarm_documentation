Swarm Behaviors
===============

ROS2swarm includes a library of swarm behaviors that are separated into movement patterns for robot motion and voting patterns for collective decision-making. 
Every pattern can either be a basic pattern (i.e., basic building blocks) or a combined pattern (i.e., using one or more patterns to create a more complex behavior). 

The different patterns may have requirements regarding the sensory setup to be executable. 
We summarize the existing patterns as well as their requirements in the following table. 


+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| Pattern                       | Domain   | Type     | Simulation          | Robot              | Sensor Requirements   |
+===============================+==========+==========+=====================+====================+=======================+
| aggregation                   | Movement | Basic    | :heavy_check_mark:  | :heavy_check_mark: | LiDAR or IR           |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| attraction                    | Movement | Basic    | :heavy_check_mark:  | :heavy_check_mark: | LiDAR or IR           |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| attraction 2                  | Movement | Basic    | :heavy_check_mark:  | :heavy_check_mark: | LiDAR or IR           |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| dispersion                    | Movement | Basic    | :heavy_check_mark:  | :heavy_check_mark: | LiDAR or IR           |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| drive                         | Movement | Basic    | :heavy_check_mark:  | :heavy_check_mark: |                       |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| magnetometer                  | Movement | Basic    | :x:                 | :heavy_check_mark: |                       |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| minimalist flocking           | Movement | Basic    | :heavy_check_mark:  | :heavy_check_mark: | LiDAR or IR           |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| random walk                   | Movement | Basic    | :heavy_check_mark:  | :heavy_check_mark: |                       |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| discussed dispersion pattern  | Movement | Combined | :heavy_check_mark:  | :heavy_check_mark: | LiDAR or IR           |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| voter model                   | Voting   | Basic    | :heavy_check_mark:  | :heavy_check_mark: |                       |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
| majority rule                 | Voting   | Basic    | :heavy_check_mark:  | :heavy_check_mark: |                       |
+-------------------------------+----------+----------+---------------------+--------------------+-----------------------+
