
# Note!
check the detail at original git https://github.com/ZJU-FAST-Lab/ego-planner


# Quick Start
Compiling tests passed on ubuntu **16.04, 18.04 and 20.04** with ros installed.
You can just execute the following commands one by one.
```
sudo apt-get install libarmadillo-dev
git clone https://github.com/beomsu7/ego-planner
cd ego-planner
sudo chmod 777 src/planner/plan_manage/scripts/trajectory_msg_converter_pos.py
# there is way to make this be done with cmakelists but not working by my self...
sudo chmod 777 src/planner/plan_manage/scripts/trajectory_msg_converter_raw.py
catkin_make
source devel/setup.bash
roslaunch ego_planner simple_run.launch 
```

for px4 sitl simulation   
   
```   
cd ego-planner
source devel/setup.bash
cd ~/PX4-Autopilot
source Tools/setup_gazebo.bash $(pwd) $(pwd)/build/px4_sitl_default
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)/Tools/sitl_gazebo
roslaunch ego_planner run_in_sitl_gazebo_px4.launch # first you need to build the uav with camera model
```


in another terminal
- rosrun mavros mavsafety arm 
- rosrun mavros mavsys mode -c OFFBOARD   

In my case to visuallize eveything, changed "world" to "map" with vscode
but the code is not edited
and you should check the gazebo world, yeah you need to change this

file:///home/hansot/Pictures/Screenshot%20from%202021-05-17%2016-50-03.png![image](https://user-images.githubusercontent.com/72853382/118452515-31b29600-b731-11eb-9709-8e2128821d4d.png)



