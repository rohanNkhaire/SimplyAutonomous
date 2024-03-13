# SimplyAutonomous
I created this repo to try out various algorithms in an Autonomous driving software stack. This stack is based on ROS2 and tested using Carla Simulator.

## Installation ##
- [SimplyAutonomous_stack](https://github.com/rohanNkhaire/SimplyAutonomous_stack.git)
    - Contains the algorithms for the AV stack.(Mapping, Localization, Perception, Planning, and Control)
- [SimplyAutonomous_utilities](https://github.com/rohanNkhaire/SimplyAutonomous_utilities.git)
    - Contains auxilary packages to help with the SimplyAutonomous_stack.
- [SimplyAutonomous_msgs](https://github.com/rohanNkhaire/SimplyAutonomous_msgs.git)
    - Contains the msgs required to pass information between nodes.
- [sim_launch](https://github.com/rohanNkhaire/sim_launch.git)
    - Contains the launch files to launch simulation in Carla simulator.
- [sample_vehicle_description](https://github.com/rohanNkhaire/sample_vehicle_description.git)
    - Contains the mesh files and URDF for the vehicle model for visualization in RVIZ

## Usage ##
```bash
# clone the repo
git clone https://github.com/rohanNkhaire/SimplyAutonomous.git

# set-up the repo
cd SimplyAutonomous
mkdir src
vcs import src < simply_autonomous.repos

# Build the repo
source /opt/ros/humble/setup.bash

# Install the dependencies
rosdep install --from-paths src -y --ignore-src
colcon build
```

## Run an example ##
```bash
# Launch the carla simulator
./CarlaUE4.sh -RenderOffScreen

# Launch the stack
ros2 launch sim_launch sim.launch.xml
```

## Note ##
I am working on ROS galactic for this repo. Autoware is a huge inspiration for me to start this project.

Currently, I am using groundtruth localization from Carla simulator to localize the vehicle.
