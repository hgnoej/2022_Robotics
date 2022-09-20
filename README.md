# Window 10

## Start
* Make packages
```
$ cd c:\opt\ros\melodic
$ mkdir robotics_ws\src
$ cd robotics_ws
$ catkin_make
```

* Install UR packages
```
$ cd ~/robotics_ws/src
$ git clone https://github.com/UniversalRobots/Universal_Robots_ROS_Driver.git src/Universal_Robots_ROS_Driver
$ git clone -b calibration_devel https://github.com/fmauch/universal_robot.git src/fmauch_universal_robot

# install dependencies
$ sudo apt update -qq
$ rosdep update
$ rosdep install --from-paths src --ignore-src -y

# build the workspace
$ cd ..
$ catkin_make
```

# Usage(UR3)
## With Simulation
```
# launch 1
# activate the workspace (ie: source it)
$ cd robotics_ws
$ source devel/setup.bash

$ cd src/fmauch_universal_robot/ur_gazebo/launch
$ roslaunch ur_gazebo ur3.launch

# launch 2
# activate the workspace (ie: source it)
$ cd robotics_ws
$ source devel/setup.bash

$ cd src/fmauch_universal_robot/ur3_moveit_config/launch
$ roslaunch ur3_moveit_planning_execution.launch sim:=true

# launch 3
# activate the workspace (ie: source it)
$ cd robotics_ws
$ source devel/setup.bash

$ cd src/fmauch_universal_robot/ur3_moveit_config/launch
$ roslaunch moveit_rviz.launch config:=true
```

* Download [Python script](https://drive.google.com/file/d/18KZmlpGgX2u60Sf9-yZ36CsdoboEqMlv/view?usp=sharing) in robotics_ws

```
# launch 4
$ python ros_test
```
