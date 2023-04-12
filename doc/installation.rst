Installation
============

This guide is a detailed step by step instruction to install the ROS2swarm package on top of *Ubuntu 20.04* for the use with 

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

	sudo apt install -y python3-pip
	pip3 install -U argcomplete
	sudo apt install python3-colcon-common-extensions python3-vcstool 

    .. group-tab:: Foxy

	sudo apt install -y python3-pip
	pip3 install -U argcomplete
	sudo apt install python3-colcon-common-extensions
        
    .. group-tab:: Galactic 

	sudo apt install -y python3-pip
	pip3 install -U argcomplete
	sudo apt install python3-colcon-common-extensions


Installation of Gazebo
----------------------

.. tabs:: 

    .. group-tab:: Dashing

	curl -sSL http://get.gazebosim.org | sh
	sudo apt remove gazebo11 libgazebo11-dev
	sudo apt install gazebo9 libgazebo9-dev
	sudo apt install ros-dashing-gazebo-ros-pkgs
	sudo apt install ros-dashing-cartographer
	sudo apt install ros-dashing-cartographer-ros
	sudo apt install ros-dashing-navigation2
	sudo apt install ros-dashing-nav2-bringup

    .. group-tab:: Foxy
    
	sudo apt install ros-foxy-gazebo-ros-pkgs
	sudo apt install ros-foxy-cartographer
	sudo apt install ros-foxy-cartographer-ros
	sudo apt install ros-foxy-navigation2
	sudo apt install ros-foxy-nav2-bringup
	
    .. group-tab:: Galactic
    
    	sudo apt install ros-galactic-gazebo-ros-pkgs
    	sudo apt install ros-galactic-cartographer
	sudo apt install ros-galactic-cartographer-ros
	sudo apt install ros-galactic-navigation2
	sudo apt install ros-galactic-nav2-bringup


Installation of Robot Packages
------------------------------

TurtleBot 3
~~~~~~~~~~~

Thymio II
~~~~~~~~~

Jackal
~~~~~~


Update of .bashrc
------------------

Update your bashrc file to include all relevant variables for running ROS2swarm 

echo 'source /opt/ros/dashing/setup.bash' >> ~/.bashrc
