# Kobuki Setup

create detailed guideline based on https://kobuki.readthedocs.io/en/release-1.0.x/software.html

1. Install the dependencies

    ```bash
    sudo apt install ros-foxy-ecl-build ros-foxy-ecl-core ros-foxy-ecl-lite ros-foxy-ecl-console ros-foxy-ecl-mobile-robot ros-foxy-angles ros-foxy-diagnostics ros-foxy-joint-state-publisher ros-foxy-testing ros-foxy-ros-testing
    ```

2. Clone this repository

    ```bash
    git clone https://github.com/AIResearchLab/kobuki.git
    ```

3. Build the system with following command. 
    ```bash
    colcon build
    ```

