# Kobuki ROS2 package

This repository and the [dependencies repository](https://github.com/AIResearchLab/kobuki_dependencies.git) focuses on merging all the public forks available on the original [Kobuki Base](https://github.com/kobuki-base) repositories and extending the work towards an complete ROS2 package for kobuki based turtlebot robots.

## Installation


1. Install the following binary dependencies

    ```bash
    sudo apt install ros-humble-angles ros-humble-diagnostics ros-humble-joint-state-publisher ros-humble-ros-testing
    ```

2. Optional Dependencies for using kobuki_keyop [Issue #21](https://github.com/ros2/teleop_twist_keyboard/issues/21)
    ```bash
    sudo apt install xterm
    ```

3. Optional Dependencies for using kobuki_joyop 
    ```bash
    sudo apt install ros-humble-teleop-twist-joy ros-humble-joy
    ```

3. Clone main repository and dependencies
    ```bash
    git clone https://github.com/AIResearchLab/kobuki.git
    git clone https://github.com/AIResearchLab/kobuki_dependencies.git
    ```

4. Build the system with following command. 
    ```bash
    colcon build
    ```

5. Set udev rule for kobuki using following commands and unplug and replug the usb cable.
    ```bash
    wget https://raw.githubusercontent.com/kobuki-base/kobuki_ftdi/devel/60-kobuki.rules
    sudo cp 60-kobuki.rules /etc/udev/rules.d

    sudo service udev reload
    sudo service udev restart
    ```

## Non-ROS usage

### Check connectivity

Run following commands in the workspace.
```bash
source ./install/setup.bash
kobuki-version-info
```

Ouput should be like,
```bash
Version Info:
Hardware Version: 1.0.4
Firmware Version: 1.2.0
Software Version: 1.1.0
Unique Device ID: 97713968-842422349-1361404194
```

### Kobuki Teleop keyboard

Run following commands in the workspace and follow onscreen instructions
```bash
source ./install/setup.bash
kobuki-simple-keyop
```

## ROS usage

### Kobuki system start

Run following commands in the workspace to start the kobuki system.
```bash
source ./install/setup.bash
ros2 launch kobuki_node kobuki_node-launch.py
```

Run following commands in the workspace to start the kobuki system as a composable node.
```bash
source ./install/setup.bash
ros2 launch kobuki_node kobuki_node-composed-launch.py
```

### Kobuki KeyOp control

Run following commands in the workspace to start kobuki system.
```bash
source ./install/setup.bash
ros2 launch kobuki_node kobuki_node-launch.py
```

Run following commands in the workspace to use kobuki keyboard control.
```bash
source ./install/setup.bash
ros2 run kobuki_keyop kobuki_keyop_node
```

### Kobuki Joystick control

Run following commands in the workspace to start kobuki system.
```bash
source ./install/setup.bash
ros2 launch kobuki_node kobuki_node-launch.py
```

Run following commands in the workspace to use kobuki keyboard control.
```bash
source ./install/setup.bash
ros2 launch kobuki_joyop kobuki_joy.launch.py
```