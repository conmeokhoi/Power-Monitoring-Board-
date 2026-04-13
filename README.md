# ESP32 Power Monitoring & Protection System

## Overview

This project features a custom-designed PCB that integrates an ESP32-WROOM-32 microcontroller with sensing and switching components to create an intelligent power management system. It provides real-time current monitoring, over-current protection (up to 10A) and IoT connectivity for remote data visualization.

![alt text](/Pic/Front.jpg)

## Technical Specifications

* Microcontroller: ESP32 (KIT ESP32 V1.3 by IoT Vision).

* Current Sensor: ACS712 Hall-effect linear current sensor.

* Switching Component: Omron G2RL-1-E High-capacity Power Relay (16A/250V).

* Connectivity: Wi-Fi (via ESP32) integrated with Blynk IoT Platform.

* Protection Logic: Hardware-software combined trip mechanism for overcurrent scenarios.

## Key Features

* Real-time Monitoring: Measures and calculates RMS current of connected AC/DC loads.

* Overload Protection: Automatically de-energizes the relay when current exceeds a predefined safety threshold to prevent device damage.

* Remote Control: Manual override to toggle the relay via the Blynk mobile app/dashboard.

* Visual Indicators: On-board LEDs for Power and Relay Status.

* Galvanic Isolation: High-voltage AC side is isolated from the low-voltage DC control side for user safety.

## Hardware Architecture

### The system is divided into two main functional blocks:

### Sensing Block & Execution Block
![alt text](/Pic/1.png)

The ACS712 outputs an analog voltage proportional to the current flow, which is sampled by the ESP32's 12-bit ADC. The Omron Relay acts as the physical circuit breaker, controlled via a transistor switching circuit from a GPIO pin.

### Control Block
![alt text](/Pic/2.png)

The ESP32 processes the raw data, applies a calibration factor, and executes the protection logic.


### Blynk Controller

Open the Blynk App to view real-time graphs and receive overload notifications.

![alt text](/Pic/3.png)

*Note: This project involves high-voltage AC (220V). Always ensure proper insulation and safety measures during testing.*
