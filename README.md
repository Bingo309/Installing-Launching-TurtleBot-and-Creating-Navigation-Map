![image](https://github.com/user-attachments/assets/0b1bdd07-0d1b-4073-ab03-270d99f57b34)# Manipulate-With-turtlesim-Package-with-ROS
This Guide to Manipulating Turtlesim Package in ROS and giving some commands.

1. Install Turtlebot packages & simulation Packages & Set up an enviorement.
   
```bash
sudo apt-get update
sudo apt-get install ros-noetic-turtlebot3
```

```bash
sudo apt-get install ros-noetic-turtlebot3-simulations
```

```bash
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
source ~/.bashrc
```

- **Start TurtleBot World:**
     ```bash
     roslaunch turtlebot3_gazebo turtlebot3_world.launch
     ```
     ![image](https://github.com/user-attachments/assets/7c941f3b-085a-4322-8762-092f2552f2d4)
     
- **Create the Map with SLAM:**
     ```bash
     roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
     ```
![image](https://github.com/user-attachments/assets/017053e6-8148-43c5-8b63-21398f5ee00e)


**Open the TurtleBot Teleoperation Node**

In a new terminal, run the teleop node to control the robot using the keyboard:

```bash
rosrun turtlebot3_teleop turtlebot3_teleop_key
```
     
     Save the map with:
     ```bash
     rosrun map_server map_saver -f ~/map
     ```
![image](https://github.com/user-attachments/assets/572b3153-3808-4997-92f3-5812b1963fe0)
![image](https://github.com/user-attachments/assets/c91aa803-4f1d-4028-a4c9-bda7914dc80d)

- **Begin Navigation:**
     ```bash
     roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
     ```
  ![image](https://github.com/user-attachments/assets/bdfa20fc-5d31-40c6-a57b-bc1edbc718b4)

