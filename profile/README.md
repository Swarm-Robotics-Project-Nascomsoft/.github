<div align="center">

#  Swarm Robotics Project - Nascomsoft
**High-Speed Sense-Plan-Act Architecture for Autonomous Robotics**

[![Status: Active Development](https://img.shields.io/badge/Status-Active_Development-brightgreen?style=for-the-badge)](#)
[![Architecture: Centralized](https://img.shields.io/badge/Architecture-Centralized_PC--Driven-blue?style=for-the-badge)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](#)

</div>

---

##  About The Organization

Welcome to our **Swarm Robotics** project developed by the [Nascomsoft](https://nascomsoft.com/) Embedded Systems Team. Our mission is to build a highly optimized, low-latency robotic fleet controlled by a centralized "Brain." Inspired by [Carnegie Mellon's PARROT project](https://github.com/PARROT-Capstone), this ecosystem relies on an overhead computer vision system, a high-speed 4D A* path planner, and lightweight robot nodes operating over a local UDP network. 

By offloading heavy computation to a central PC, our physical robots are incredibly lightweight, affordable, and capable of operating in dense swarms without localized collisions.

---

##  System Architecture & Repositories

Our organization is divided into three core pillars. Each repository contains specific documentation for its respective domain.

###  1. [Motion & Vision (The Brain)](https://github.com/Swarm-Robotics-Project-Nascomsoft/motion-vision-controller)
**The centralized command center running on the host PC.**
*   **Vision:** Uses an overhead camera and OpenCV ArUco tracking to pinpoint robot and payload coordinates (X, Y, Theta) in real-world millimeters.
*   **Motion Planner:** A highly parallelized 4D A* search algorithm written in C++ that calculates collision-free routing in real-time.
*   **Controller:** A Python-based feedforward/feedback controller utilizing cubic Hermite splines to guarantee smooth kinematics and UDP network broadcasting.

###  2. [Robot Firmware (The Nerves)](https://github.com/Swarm-Robotics-Project-Nascomsoft/firmware)
**The low-level C/C++ code executing on the microcontrollers.**
*   **Networking:** Handles low-latency UDP packet reception and implements dead-man switch failsafes.
*   **Kinematics:** Translates global velocity vectors into localized Left/Right wheel speeds.
*   **Hardware Control:** Manages localized PID loops using wheel encoders and toggles payload mechanisms (electromagnets).

###  3. [Robot Hardware (The Muscle)](https://github.com/Swarm-Robotics-Project-Nascomsoft/hardware)
**The physical manifestation of the robots.**
*   **Mechanical:** 3D CAD files for the chassis, motor mounts, and the payload handling mechanisms.
*   **Electrical:** Custom PCB schematics, motor driver integration, and battery management logic.
*   **Environment:** Arena build specifications, ArUco marker print files, and lighting setup.

---

##  Technology Stack

We leverage a hybrid stack to maximize performance where it matters, and maintain readability where it doesn't. 

### Motion & Vision
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=for-the-badge&logo=opencv&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-%23008FBA.svg?style=for-the-badge&logo=cmake&logoColor=white)

### Firmware & Hardware
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![PlatformIO](https://img.shields.io/badge/PlatformIO-F6822C?style=for-the-badge&logo=PlatformIO&logoColor=white)
![Espressif](https://img.shields.io/badge/ESP32-E7352C?style=for-the-badge&logo=espressif&logoColor=white)
![Autodesk Fusion 360](https://img.shields.io/badge/Fusion%20360-%23F6822C.svg?style=for-the-badge&logo=autodesk&logoColor=white)
![KiCad](https://img.shields.io/badge/KiCad-%23FFFFFF.svg?style=for-the-badge&logo=kicad&logoColor=black)

---

##  Quick Start for New Contributors

If you have just been added to the GitHub organization, follow these steps to get your local environment running:

1. **Pick Your Domain:** Request access to the specific repository you are assigned to (Vision/Motion, Firmware, or Hardware).
2. **Clone the Repo:** 
   ```bash
   git clone [https://github.com/Swarm-Robotics-Project-Nascomsoft/](https://github.com/Swarm-Robotics-Project-Nascomsoft)[repository-name].git