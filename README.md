# Totorobot
A voice controlled tour guiding robot

## Dependencies
Totorobot requires the flowing dependencies:
* [flask-ask](https://alexatutorial.com/flask-ask/)

And for simulation:
* [`fetch_ros`](https://github.com/fetchrobotics/fetch_ros)
* [`fetch_gazebo`](https://github.com/fetchrobotics/fetch_gazebo)

If you can't install the fetch packages from apt, you can build them within your catkin workspace. On top of a base ROS install, you may need a few additional packages:

``` terminal
sudo apt-get install \
ros-kinetic-opencv-candidate \
ros-kinetic-moveit* \
ros-kinetic-robot-controllers* \
ros-kinetic-navigation*
```

## Installation
Create a catkin workspace:

``` terminal
mkdir caktin_ws && cd caktin_ws
catkin init
```

Clone this repo into the source directory, as well as any fetch packages if needed,
and build

``` terminal
mkdir src && cd src
git clone https://github.com/CogRob/totorobot
catkin build
```

# Running
To test using the simulation, configure the alexa skills like you would from [this tutorial](https://developer.amazon.com/public/community/post/Tx14R0IYYGH3SKT/Flask-Ask-A-New-Python-Framework-for-Rapid-Alexa-Skills-Kit-Development). The skill files are located under the skills folder in the totorobot package.

To start the playground simulation, we'll go ahead and launch it using the gazebo package:

``` terminal
roslaunch totorobot_gazebo totorobot_gazebo.launch
```

We should be now able to move about totorobot using a joypad, see totorobot_teleop launch files for defaults. You can also launch the rviz interface customized for totorobot using the launch files in totorobot_rviz:

``` terminal
roslaunch totorobot_rviz view_totorobot.launch
```

To launch the voice logic and touring in the playground simulation, we'll using another launch file to start the tour.

``` terminal
roslaunch totorobot totorobot_tour.launch
```
