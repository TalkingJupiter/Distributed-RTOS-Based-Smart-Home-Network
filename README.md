# Distributed RTOS-Based Smart Home Network

## Overview
This project implements a distributed smart home automation system using multiple ESP32 microcontrollers running FreeRTOS, Each ESP32 device responsible for controlling or monitoring part of a home (e.g, sensors or relays) amd communicates with other devices through an MQTT broker. The system showcases embedded design, RTOS task management, real time communciation, and IOT networking using C and C++.

## Technologies Used
- **ESP32** (Devkit boards)
- **FreeRTOS** (real time OS on each microcontroller)
- **MQTT** (lightweight publish/subscribe messaging protocol)
- **Mosquitto Broker** (can be local on Raspberry Pi or cloud)
- **C & C++** (for task logic, drivers, and abstraction layers)
- **PlatformIO / ESP-IDF** (toolchain)

## System Architecture
```
*------------------*        *------------------* 
| Sensor Node (A)  |        | Actuato Node (B) |
| - Temp & Motion  |        | - Light/Fan Relay|
| - Publishes data |        | - Subscribes to  |
|   to MQTT topics |        |   commands       |
*------------------*        *------------------*
        \                               /
         \                             /
         *------------------------------*
         |  MQTT Broker(Raspberry Pi)   |
         |  or HiveMQ Cloud             |
         *------------------------------* 
                        |
                *-------------*  
                | Control GUI |
                *-------------*  
```
