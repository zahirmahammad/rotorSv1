# rotorSv1 
updated the rotorS Package - https://github.com/ethz-asl/rotors_simulator

Installation - Ubuntu 20.04 with ROS Noetic and Gazebo 11
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
![Screenshot 2023-09-20 004332](https://github.com/zahirmahammad/rotorSv1/assets/61276650/1abd0ba9-c036-4173-bcc7-96508fae7973)

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
![Screenshot 2023-09-20 004522](https://github.com/zahirmahammad/rotorSv1/assets/61276650/9eed94b8-130d-4559-b7d5-7ce8cf773842)

To spawn F550 Swarm in gazebo
```
source devel/setup.bash
roslaunch rotors_gazebo f550_swarm_hovering_example.launch
```
![Screenshot 2023-09-20 004754](https://github.com/zahirmahammad/rotorSv1/assets/61276650/5b094e44-8696-43a5-89a7-7fe6f23ca1ee)

Navigate into /CrazyS/rotors_gazebo/launch/ folder to go through various the launch files

To spawn other drone models use the below command (note that xxx should be replaced with the model name)
```
roslaunch rotors_gazebo xxx_hovering_example.launch
roslaunch rotors_gazebo xxx_swarm_hovering_example.launch #spawns the swarm of drone model
```

To spawn all the drones in the package
```
source devel/setup.bash
roslaunch rotors_gazebo all_multicopters_hovering_example.launch
```

![Screenshot 2023-09-20 011319](https://github.com/zahirmahammad/rotorSv1/assets/61276650/f7985352-b634-426a-878a-43fc5abb3eab)

![ezgif com-video-to-gif (1)](https://github.com/zahirmahammad/rotorSv1/assets/61276650/a94a0a52-3283-4bbf-8b03-5cbc0c5b7cbb)


