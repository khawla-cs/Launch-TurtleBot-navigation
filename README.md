note : i am using ROS noetic

## Install ROS on Remote PC
```
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh
$ chmod 755 ./install_ros_noetic.sh 
$ bash ./install_ros_noetic.sh
```

![image](https://github.com/user-attachments/assets/6ce3c9b3-91e8-409d-9f7e-0c1238d98b12)

## Install Dependent ROS Packages 
it is important!
```
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```

![Screenshot 2024-07-19 081643](https://github.com/user-attachments/assets/6ae7c6bd-1be5-46b0-a999-268e4be27694)

## Install TurtleBot3 Packages

```
$ sudo apt install ros-noetic-dynamixel-sdk
```

![Screenshot 2024-07-19 082035](https://github.com/user-attachments/assets/c300cb3a-a8ad-4a53-abb4-d5e32ed6bc5b)

```
$ sudo apt install ros-noetic-turtlebot3-msgs
```

![Screenshot 2024-07-19 082242](https://github.com/user-attachments/assets/95babab8-d526-4063-a955-5e995e3b7e3e)

```
$ sudo apt install ros-noetic-turtlebot3
```

![Screenshot 2024-07-19 082511](https://github.com/user-attachments/assets/33e2787b-aa3c-4435-979c-9184321ce9dd)

##  Catkin workspace


![Screenshot 2024-07-19 083509](https://github.com/user-attachments/assets/c14b3842-70aa-428a-a73c-d110e983ea9f)

## Launch Simulation World in Gazebo
you can choose one of these:

1. Empty World
   
2.TurtleBot3 World
  
3.TurtleBot3 House 

for me, i have choose the second one so i will run this command

```
$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

![Screenshot 2024-07-19 084227](https://github.com/user-attachments/assets/23254b87-1b1d-4dfe-9399-306eb347ed41)


## Opening SLAM
```
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```

<img width="1398" alt="88" src="https://github.com/user-attachments/assets/e7ddcd40-6a8c-4f18-bb72-1b85f581c149">

create a map and save it
```
rosrun map_server map_saver -f ~/map
```
then run this command:
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```


<img width="1052" alt="89" src="https://github.com/user-attachments/assets/706387dc-80f4-4584-b85a-a2db67a8d93d">

## navigation
start the navigation and load the saved map, using this command:
```
roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:='/home/muh/map.yaml'
```

<img width="685" alt="90" src="https://github.com/user-attachments/assets/308a42e4-aaf7-45d9-be9f-dfd693290f67">

now You can then move the robot !


<img width="440" alt="image" src="https://github.com/user-attachments/assets/ea6b0965-98b3-4cbf-a873-f97680e73edc">

