🤖 Yuvaan IITG Rover — Electronics & Control System

Welcome to the repository of the Yuvaan IITG Rover, designed for the International Rover Challenge (IRC) 2025. This document focuses on the Electronics, Power, Communication, and Software Control systems that power our rover’s mission-critical functions.

⚡ Power Distribution System

Main Power:

Three Li-Po batteries (25,000 mAh, 22.2V, 25C) connected in series to power all subsystems.

Sub-systems powered:

✅ Ground Vehicle

✅ Robotic Arm

✅ Astrobiology Assembly

Emergency Kill-Switch: Disconnects power instantly in critical situations for safety.

PCB Design: Custom-designed PCB ensures organised connections, minimises signal loss, and provides stable voltage distribution.



🧠 Control System Architecture

Onboard Computer: NVIDIA Jetson Orin Nano

Microcontrollers: Arduino Mega and Arduino Uno (for various subsystems)

Motor Drivers: Cytron MDD20A, L298N

Sensors: pH, NPK, BME280, Spectrometer, MQ2 Gas Sensor, USB Microscope, Soil Moisture Sensor

Cameras: ZED Camera, Intel RealSense, Webcams



📡 Communication System

Antenna setup:
Access Point (Base Station) ↔ Client (Rover) Wi-Fi configuration

ROS Network:
ROS servers on Jetson and base station manage data flow; firewall rules ensure security

Automation:
Bash scripts automate key operations (sensor/motor initialisation, mode switching)


💻 Software & Control

ROS Noetic Framework for seamless subsystem integration

Manual Mode: Gamepad-based direct control


Autonomous Mode:
YOLO + ResNet pipeline for arrow detection and direction classification
ZED camera for distance estimation
ROS topics for command publishing


Rover Control Centre:
Web-based dashboard using Flask + JS
Live panoramic video, speed, joint positions, and error logs


## 🚀 Key Components Summary

| 🏷️ Component            | ⚡ Details                                                   |
|-------------------------|-------------------------------------------------------------|
| **Main Computer**        | NVIDIA Jetson Orin Nano                                     |
| **Microcontrollers**     | Arduino Mega, Arduino Uno                                   |
| **Motor Drivers**        | Cytron MDD20A, L298N                                        |
| **Power**                | 3x Li-Po (25,000 mAh, 22.2V, 25C)                           |
| **Main Sensors**         | pH, NPK, BME280, Spectrometer, MQ2 Gas Sensor, USB Microscope |
| **Cameras**              | ZED Camera, Intel RealSense, Webcams                        |
| **Communication**        | ROS over Wi-Fi (Access Point + Client setup)                |
| **Emergency Protection** | Hardware kill switch                                        |



🛠️ Electronics Architecture Diagram
mathematica
Copy
Edit
                      ┌────────────────────────────┐
                      │        Base Station         │
                      │ Gamepad + Rover Control UI │
                      │ ROS Server + Video Stream  │
                      └────────────┬───────────────┘
                                   │ Wi-Fi (Access Point / Client)
                                   │
                ┌─────────────────▼──────────────────┐
                │         Jetson Orin Nano            │
                │ ROS Node Master + AI Processing     │
                │ (YOLO + ResNet + Control Logic)     │
                └───────┬──────────────┬──────────────┘
                        │              │
           ┌────────────▼──┐        ┌───▼──────────────┐
           │ Arduino Mega  │        │ Arduino Mega /   │
           │ (Ground Rover │        │ Uno (Bio Module) │
           │  & Arm Ctrl)  │        │                  │
           └─────┬─────────┘        └─────┬────────────┘
                 │                         │
     ┌───────────▼───────────┐  ┌──────────▼──────────┐
     │ Motor Drivers:        │  │ Motor Drivers +     │
     │ Cytron MDD20A / L298N │  │ Linear Actuators    │
     └───────────────────────┘  └────────────────────┘
                 │                         │
          Wheels + Steering          Drill + Gripper + Sensors







🤝 Contributions
We welcome collaborators interested in:

Enhancing power efficiency

Improving autonomous control algorithms

Designing optimised PCBs
