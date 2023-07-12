# rotorSv1
Added f550 drone in existing CrazyS package


Download the code into the xxx/xxx/src folder



```
mkdir catkin_ws
cd catkin_ws
mkdir src
cd src
git clone https://github.com/zahirmahammad/rotorSv1.git
cd ..
```

Build the package using the following command
```
catkin build
```

Launch the F550 drone in gazebo
```
source devel/setup.bash
roslaunch rotors_gazebo f550_hovering_example.launch
```

Navigate into /CrazyS/rotors_gazebo/launch/ folder to go through various the launch files

F550 Swarm in gazebo
```
source devel/setup.bash
roslaunch rotors_gazebo f550_swarm_hovering_example.launch
