# gym_install
Conda environment installation files for Gazebo GYM Reinforcement Learning [toolkit](https://github.com/erlerobot/gym-gazebo) .

### 1. Upgrade to Gazebo 8
    sudo apt-get remove ros-kinetic-gazebo* 
    sudo apt-get upgrade
    sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
    wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
    sudo apt-get update
    sudo apt-get -y install ros-kinetic-gazebo8*

### 2. Installation
    git clone https://github.com/grassjelly/gym_install
    cd gym_install
    ./installgym

### 3. Gazebo Visualization
Set gui arg to true:

    cd $HOME/gym-gazebo/gym_gazebo/envs/assets/launch
    nano GazeboCircuit2TurtlebotLidar_v0.launch

### 4. Run Turtlebot sample code
Open a new terminal and run:

    gym_ws
    cd $HOME/gym-gazebo/examples/turtlebot
    python circuit2_turtlebot_lidar_qlearn.py

