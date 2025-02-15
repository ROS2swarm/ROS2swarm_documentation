Sensor Layer 
============

ROS2swarm provides several sensor layers to enable the use of robots with different sensor setups:

* lidar_layer
* ir_layer
* ir_tf_layer

The sensor layer receives the sensor data from the respective sensors and transforms it to a RangeData message.

.. code-block:: none

	std_msgs/Header header
	float32[] ranges
	float64[] angles

The RangeData message contains two arrays: (i) the measured distances or ranges and (ii) the angle of the measurement (e.g., position of IR sensor). 
The parameters of the sensor layer can be specified in the config file ``sensor_specification.yaml``. 
New sensor layers can be easily integrated.

