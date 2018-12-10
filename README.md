# gym_install
Conda environment installation files for Gazebo GYM Reinforcement Learning [toolkit](https://github.com/erlerobot/gym-gazebo) .

### 1. Upgrade to Gazebo 8
    sudo apt-get remove ros-kinetic-gazebo* 
    sudo apt-get upgrade
    sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
    wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
    sudo apt-get update
    sudo apt-get -y install ros-kinetic-gazebo8*

### 2. Installation:
    git clone https://github.com/grassjelly/gym_install
    cd gym_install
    ./installgym

### 3. Set GUI to true:
    cd $HOME/gym-gazebo/gym_gazebo/envs/assets/launch
    nano GazeboCircuit2TurtlebotLidar_v0.launch

### 4. Run Turtlebot sample code:
    gym_ws
    cd $HOME/gym-gazebo/examples/turtlebot
    python circuit2_turtlebot_lidar_qlearn.py

### 5. Troubleshooting:
If the sample code runs on Python 2.7 create a new Python 3 conda environment and rebuild the workspace

    source $HOME/miniconda3/etc/profile.d/conda.sh
    conda create --name p3-env pip python=3 --yes
    conda activate p3-env
    yes | pip install catkin_pkg rospkg pyyaml empy 
    cd $HOME/gym-gazebo/gym_gazebo/envs/installation/catkin_ws
    rm -rf devel
    rm -rf build
    catkin_make --cmake-args -DCMAKE_CXX_STANDARD=11
