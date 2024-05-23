# Kobuki Setup

create detailed guideline based on https://kobuki.readthedocs.io/en/release-1.0.x/software.html

1. Install the dependencies

    ```bash
    sudo apt install ros-humble-ecl-build ros-humble-ecl-core ros-humble-ecl-lite ros-humble-ecl-console ros-humble-ecl-mobile-robot ros-humble-angles ros-humble-diagnostics ros-humble-joint-state-publisher ros-humble-testing ros-humble-ros-testing
    ```

2. Clone this repository

    ```bash
    git clone https://github.com/AIResearchLab/kobuki.git
    ```

3. Build the system with following command. 
    ```bash
    colcon build
    ```

