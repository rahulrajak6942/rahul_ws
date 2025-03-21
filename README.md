# Mobile Robot

This repository consists of a mobile robot equipped with an RGB camera and a LiDAR sensor. The robot can be teleoperated using a keyboard and includes a filtering mechanism to restrict the LiDAR sensor's field of view (FOV) to 120 degrees.

## Features
- RGB Camera and LiDAR integration
- Keyboard teleoperation
- LiDAR data filtering (120-degree FOV restriction)
- Simulation support in Gazebo and Rviz2

## Repository Structure
### 1. bot_description
This package contains the robot description and launch files:
- **`rviz.launch.py`** – Spawns the robot URDF in Rviz2 for visualization.
- **`spawn.launch.py`** – Spawns the robot in an empty world in Gazebo.
- **`control.launch.py`** – Runs the `teleop_twist_keyboard` node, allowing keyboard control of the robot.

### 2. bot_world
This package defines a custom Gazebo world for the robot:
- **`world.launch.py`** – Spawns the robot in a custom Gazebo world.

### 3. bot_control
This package manages the robot’s control and sensor filtering:
- **`filter.launch.py`** – Spawns the robot in a custom Gazebo world, starts the LiDAR filtering node (restricting FOV to 120 degrees), and launches Rviz2 for visualization.

## Installation & Usage
### Prerequisites
Ensure you have ROS 2 and Gazebo installed on your system.

### Clone the Repository
```bash
cd ~/your_ros2_ws/src
git clone https://github.com/rahulrajak6942/rahul_ws.git
cd ..
colcon build
source install/setup.bash
```

### Running the Simulation
1. **View Robot in Rviz2:**
   ```bash
   ros2 launch bot_description rviz.launch.py
   ```
2. **Spawn Robot in Gazebo:**
   ```bash
   ros2 launch bot_description spawn.launch.py
   ```
3. **Control the Robot Using Keyboard:**
   ```bash
   ros2 launch bot_description control.launch.py
   ```
4. **Spawn Robot in a Custom World:**
   ```bash
   ros2 launch bot_world world.launch.py
   ```
5. **Run LiDAR Filtering and Visualization:**
   ```bash
   ros2 launch bot_control filter.launch.py
   ```


## Author
[**Rahul Rajak**](https://github.com/rahulrajak6942)



