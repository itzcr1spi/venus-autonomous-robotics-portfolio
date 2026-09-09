# Engineering Challenge for Venus | Autonomous Multi-Robot Rover

An embedded-systems project in which two autonomous rover robots explored an unknown simulated Venus environment, identified rock samples and transmitted live mission data to a base-station map.

> **Publication note**  
> This repository contains my own portfolio documentation, recreated diagrams and simplified examples. It excludes shared team source code, course-provided libraries, compiled binaries, raw data and the original course submission.

## Overview

The project integrated autonomous navigation, multi-sensor data acquisition, embedded C programming, wireless communication and a Python-based mission-control interface.

Two robots independently explored the terrain, detected obstacles and boundaries, classified rock samples, measured ambient temperature and sent their observations to a base station for real-time visualisation.

## My Contribution

I contributed to embedded systems and system-integration work across the PYNQ rover platform, ESP32 communication link, sensor-driven behaviour and testing.

This involved working with C, PYNQ, ESP32, UART, MQTT, sensor integration and autonomous rover behaviour.

## System Architecture

```text
Sensors
(VL53L0X, TCS3200, NTC, TCRT5000)
                 ↓
PYNQ-Z2 rover controller
Embedded C and navigation state machine
                 ↓ UART
ESP32 communication bridge
                 ↓ MQTT
Python mission control and graphical map
```

## Autonomous Behaviour

The rover used a reactive state machine:

```text
SCAN → APPROACH → EVALUATE → ROAM
```

- **SCAN:** rotate and identify possible rock samples
- **APPROACH:** navigate towards a detected sample while avoiding obstacles
- **EVALUATE:** classify colour, measure temperature and report findings
- **ROAM:** move to a new area when no sample is detected
- **Boundary response:** reverse, turn and resume exploration when black tape is detected

## Engineering Highlights

- Integrated three VL53L0X time-of-flight sensors on a shared I2C bus.
- Used controlled startup and XSHUT pins to assign unique sensor addresses.
- Used a TCS3200 colour sensor to classify rock samples.
- Used an NTC-10K thermistor and ADC measurement for temperature sensing.
- Used TCRT5000 infrared sensors to detect boundaries and crater edges.
- Implemented UART communication between PYNQ and ESP32.
- Used MQTT for telemetry, mission-control updates and coordination between two rovers.
- Built a Python-based mission-control interface for live mapping and robot telemetry.
- Designed fault handling for boundaries, communication loss and invalid sensor data.

## Testing and Results

The system was tested from individual components through integrated subsystems and full operation on the physical Venus mock-up terrain.

Validated capabilities included:

- Autonomous terrain exploration
- Obstacle and boundary avoidance
- Rock-sample detection and colour classification
- Temperature measurement
- Sensor-data transmission through MQTT
- Real-time base-station map updates

## Technologies

C · Python · PYNQ-Z2 · ESP32 · UART · MQTT · I2C · GPIO · ADC · VL53L0X · TCS3200 · TCRT5000 · Embedded Systems

## Repository Contents

- `docs/` — system architecture, test approach and engineering decisions
- `assets/` — recreated diagrams and approved test visuals
- `examples/` — small, independently written embedded or communication examples
- `README.md` — project overview
