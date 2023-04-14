Installation
============

This guide is a detailed step by step instruction to install the ROS2swarm package on top of *Ubuntu* for the use with 

- the TurtleBot 3
- the Jackal UGV or
- the Thymio II

Prerequisistes
--------------

.. tabs:: 

    .. group-tab:: Dashing

        Ubuntu 18.04

    .. group-tab:: Foxy

        Ubuntu 20.04
        
    .. group-tab:: Galactic 

        Ubuntu 20.04 


Installation of ROS 2
---------------------

ROS2swarm currently supports ROS 2 Dashing, Foxy, and Galactic. 

Please install your desired ROS 2 version (recommended: Galactic) following the official ROS 2 installation guide: 


.. tabs:: 

    .. group-tab:: Dashing

        `Installing ROS 2 Dashing Diademata <https://docs.ros.org/en/dashing/Installation/Ubuntu-Install-Debians.html>`_ 

    .. group-tab:: Foxy

        `Installing ROS 2 Foxy Fitzroy <https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html>`_ 
        
    .. group-tab:: Galactic 

        `Installing ROS 2 Galactic Geochelone <https://docs.ros.org/en/galactic/Installation/Ubuntu-Install-Debians.html>`_ 



Installation of Additional Dependencies
---------------------------------------

.. tabs:: 

    .. group-tab:: Dashing
    
	.. code-block:: console
	
		sudo apt install -y python3-pip
		pip3 install -U argcomplete
		sudo apt install python3-colcon-common-extensions python3-vcstool 

    .. group-tab:: Foxy
    
	.. code-block:: console
	
		sudo apt install -y python3-pip
		pip3 install -U argcomplete
		sudo apt install python3-colcon-common-extensions
        
    .. group-tab:: Galactic 
    
	.. code-block:: console
	
		sudo apt install -y python3-pip
		pip3 install -U argcomplete
		sudo apt install python3-colcon-common-extensions


Installation of Gazebo
----------------------

.. tabs:: 

    .. group-tab:: Dashing
    
		.. code-block:: console
	
			curl -sSL http://get.gazebosim.org | sh
			sudo apt remove gazebo11 libgazebo11-dev
			sudo apt install gazebo9 libgazebo9-dev
			sudo apt install ros-dashing-gazebo-ros-pkgs
			sudo apt install ros-dashing-cartographer ros-dashing-cartographer-ros
			sudo apt install ros-dashing-navigation2 ros-dashing-nav2-bringup

    .. group-tab:: Foxy
    
    	.. code-block:: console
    	
			sudo apt install ros-foxy-gazebo-ros-pkgs
			sudo apt install ros-foxy-cartographer ros-foxy-cartographer-ros
			sudo apt install ros-foxy-navigation2 ros-foxy-nav2-bringup
	
    .. group-tab:: Galactic
    
    	.. code-block:: console
    	
    		sudo apt install ros-galactic-gazebo-ros-pkgs
    		sudo apt install ros-galactic-cartographer ros-galactic-cartographer-ros
			sudo apt install ros-galactic-navigation2 ros-galactic-nav2-bringup


Installation of Robot Packages
------------------------------

TurtleBot 3
~~~~~~~~~~~

.. tabs:: 

    .. group-tab:: Dashing
    
		.. code-block:: console
	
			mkdir -p ~/turtlebot3_ws/src
			cd ~/turtlebot3_ws/src/
			git clone -b dashing-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
			git clone -b dashing-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
			sudo apt install ros-dashing-dynamixel-sdk
			git clone -b dashing-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
			cd ~/turtlebot3_ws && colcon build --symlink-install	


    .. group-tab:: Foxy
    
    	.. code-block:: console
    	
			mkdir -p ~/turtlebot3_ws/src
			cd ~/turtlebot3_ws/src/
			git clone -b foxy-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
			git clone -b foxy-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
			sudo apt install ros-foxy-dynamixel-sdk
			git clone -b foxy-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
			cd ~/turtlebot3_ws && colcon build --symlink-install
		
    .. group-tab:: Galactic
    
    	.. code-block:: console
    		
	    	mkdir -p ~/turtlebot3_ws/src
			cd ~/turtlebot3_ws/src/
			git clone -b galactic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
			git clone -b galactic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git
			sudo apt install ros-galactic-dynamixel-sdk
			git clone -b galactic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
			cd ~/turtlebot3_ws && colcon build --symlink-install



Thymio II
~~~~~~~~~

.. tabs:: 

	.. group-tab:: Dashing

		No Thymio II support 

	.. group-tab:: Foxy

		1. Please follow the official `installation guide  <http://jeguzzi.github.io/ros-aseba/installation.html#ros-aseba>`_ for ROS-Aseba (simulation and real robots) and ROS-Thymio (real robots only).
		2. Clone the Thymio description repository to your colcon workspace 
			
		.. code-block:: console

			git clone https://github.com/ROS2swarm/thymio_description.git src/thymio_description 

		3. Build your colcon workspace 

		.. code-block:: console

			colcon build --symlink-install 		

	.. group-tab:: Galactic

		follow instructions for foxy (untested!)
    	

Jackal
~~~~~~

.. tabs:: 

	.. group-tab:: Dashing

		No Jackal support 

	.. group-tab:: Foxy

	 	Please follow the official `installation guide <http://www.clearpathrobotics.com/assets/guides/foxy/jackal/JackalInstallDesktopSoftware.html#installing-jackal-desktop-software>`_.

		Set the parameters for including a LiDAR:

		.. code-block:: console

			echo 'export JACKAL_LASER=1' >> ~/.bashrc
			echo 'export JACKAL_LASER_MOUNT=mid' >> ~/.bashrc
	
	.. group-tab:: Galactic

		No Jackal support 


Environment Configuration 
-------------------------

.. tabs:: 

    .. group-tab:: Dashing
    
		.. code-block:: console
	
			echo 'source /opt/ros/dashing/setup.bash' >> ~/.bashrc	
			echo 'source /~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc
			echo 'export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:~/turtlebot3_ws/src/turtlebot3_simulations/turtlebot3_gazebo/models:~/turtlebot3_ws/src/thymio_description' >> ~/.bashrc
			echo 'export TURTLEBOT3_MODEL=waffle_pi' >> ~/.bashrc
				
    .. group-tab:: Foxy
    
    	.. code-block:: console
    	
			echo 'source /opt/ros/foxy/setup.bash' >> ~/.bashrc
			echo 'source /~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc
			echo 'export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:~/turtlebot3_ws/src/turtlebot3_simulations/turtlebot3_gazebo/models' >> ~/.bashrc
			echo 'export TURTLEBOT3_MODEL=waffle_pi' >> ~/.bashrc
		
    .. group-tab:: Galactic
    
    	.. code-block:: console
    		
			echo 'source /opt/ros/galactic/setup.bash' >> ~/.bashrc
			echo 'source /~/turtlebot3_ws/install/setup.bash' >> ~/.bashrc
			echo 'export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:~/turtlebot3_ws/src/turtlebot3_simulations/turtlebot3_gazebo/models' >> ~/.bashrc
			echo 'export TURTLEBOT3_MODEL=waffle_pi' >> ~/.bashrc

