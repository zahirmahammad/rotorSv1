# rotorSv1
CrazyS package Updated
Installation Instructions - Ubuntu 20.04 with ROS Noetic and Gazebo 11
-----------------------------------------------------------------------
To use the code developed and stored in this repository some preliminary actions are needed. They are listed below.

1. Install and initialize ROS noetic desktop full, additional ROS packages, catkin-tools, and wstool:

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-noetic-desktop-full ros-noetic-joy ros-noetic-octomap-ros ros-noetic-mavlink
sudo apt install ros-noetic-octomap-mapping ros-noetic-control-toolbox
sudo apt install python3-vcstool python3-catkin-tools protobuf-compiler libgoogle-glog-dev
sudo rosdep init
rosdep update
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt-get install python3-rosdep python3-wstool ros-noetic-ros libgoogle-glog-dev
```

Download the code into the xxx/xxx/src folder

Follow the given commands

```
mkdir ~/rotors_ws/src
cd ~/rotors_ws/src
git clone https://github.com/zahirmahammad/rotorSv1.git
cd ..
```

Build the package using the following command
```
cd ~/rotors_ws/
catkin build
```

    
**Launch firefly drone in gazebo**
```
source devel/setup.bash
roslaunch rotors_gazebo mav_hovering_example.launch mav_name:=firefly world_name:=basic
```
To spwan swarm of firefly drone use
```
roslaunch rotors_gazebo firefly_swarm_hovering_example.launch
```
New List of drones
1) hummingbird
2) pelican
3) firefly
4) f450
5) f550
6) s500
7) tarot650
8) tarot680
9) x500
    
**Launch the F550 drone in gazebo**
```
source devel/setup.bash
roslaunch rotors_gazebo f550_hovering_example.launch
```
To spawn F550 Swarm in gazebo
```
source devel/setup.bash
roslaunch rotors_gazebo f550_swarm_hovering_example.launch
```

Navigate into /CrazyS/rotors_gazebo/launch/ folder to go through various the launch files


