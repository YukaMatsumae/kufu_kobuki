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

