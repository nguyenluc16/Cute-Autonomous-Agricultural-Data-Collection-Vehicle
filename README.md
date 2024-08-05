# Cute Autonomous Agricultural Data Collection Vehicle with STM32F103C8T6 

This project involves the design and implementation of an autonomous vehicle aimed at collecting agricultural environmental data. The vehicle is equipped with various sensors and uses advanced algorithms to navigate and map the environment, while collecting crucial data to assist in agricultural monitoring and decision-making.

## Table of Contents
- [Introduction](#introduction)
- [Hardware Components](#hardware-components)
- [Software Components](#software-components)
- [Algorithms](#algorithms)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The autonomous vehicle is designed to:
- Navigate autonomously in an agricultural environment.
- Collect environmental data using various sensors.
- Map the environment using SLAM (Simultaneous Localization and Mapping).
- Plan routes and avoid obstacles using DWA (Dynamic Window Approach).

## Hardware Components

- **Microcontroller**: STM32F1
- **Embedded Computer**: Linux Ubuntu OS
- **Motor Controller**: PID-based motor control
- **Sensors**:
  - LiDAR for mapping and obstacle detection
  - DHT11 for temperature and humidity data
  - M9BI for additional environmental data
- **Communication Module**: ESP32 using MQTT protocol
- **Platform**: 3-wheeled vehicle with differential drive

## Software Components

- **ROS (Robot Operating System)**: For handling positioning, mapping, and route planning
- **Blynk Platform**: For remote data monitoring and control
- **Linux**: The ROS platform runs on a Linux-based system

## Algorithms

- **Movement Control Algorithm**: Manual or autonomous control of the three-wheeled vehicle with differential drive.
- **SLAM (Simultaneous Localization and Mapping)**: Uses a laser sensor (LiDAR) for creating a map of the environment.
- **ALS (Autonomous Localization System)**: Determines the vehicle's position on the map.
- **DWA (Dynamic Window Approach)**: Plans a path to avoid obstacles based on the generated map.
- **PID Control**: For precise motor control.

## Setup and Installation

### Hardware Setup

1. **Assemble the Vehicle**: Attach the wheels, motors, and sensors to the vehicle chassis.
2. **Connect the Microcontroller**: Connect the STM32F1 microcontroller to the motor drivers and sensors.
3. **Setup Communication Module**: Connect the ESP32 module to the STM32F1 for MQTT communication.

### Software Installation

1. **ROS Installation**
    - Follow the [official ROS installation guide](http://wiki.ros.org/ROS/Installation) for your Linux distribution.
2. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/agri-autonomous-vehicle.git
    cd agri-autonomous-vehicle
    ```
3. **Install Dependencies**
    - Use `rosdep` to install dependencies:
    ```bash
    rosdep install --from-paths src --ignore-src -r -y
    ```
4. **Build the Workspace**
    ```bash
    catkin_make
    source devel/setup.bash
    ```

## Usage

1. **Launching the ROS Nodes**
    - Start the ROS master:
    ```bash
    roscore
    ```
    - Launch the SLAM algorithm:
    ```bash
    roslaunch your_package slam.launch
    ```
    - Launch the DWA planner:
    ```bash
    roslaunch your_package dwa_planner.launch
    ```
2. **Remote Monitoring**
    - Use the Blynk app to connect to the vehicle using the ESP32 module.

## Contributing

Contributions are welcome! Please submit pull requests or open issues to improve the project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
