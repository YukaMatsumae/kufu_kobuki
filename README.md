# Kobuki Setup

create detailed guideline based on https://kobuki.readthedocs.io/en/release-1.0.x/software.html

1. Install the following binary dependencies

    ```bash
    sudo apt install ros-humble-angles ros-humble-diagnostics ros-humble-joint-state-publisher ros-humble-ros-testing
    ```

2. Clone main repository and dependencies
    ```bash
    git clone https://github.com/AIResearchLab/kobuki.git
    git clone https://github.com/AIResearchLab/kobuki_dependencies.git
    ```

3. Build the system with following command. 
    ```bash
    colcon build
    ```

4. Set udev rule for kobuki using following commands and unplug and replug the usb cable.
    ```bash
    wget https://raw.githubusercontent.com/kobuki-base/kobuki_ftdi/devel/60-kobuki.rules
    sudo cp 60-kobuki.rules /etc/udev/rules.d

    sudo service udev reload
    sudo service udev restart
    ```

5. Check connectivity
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

6. Kobuki Teleop keyboard

    ```bash
    source ./install/setup.bash
    kobuki-simple-keyop
    ```