# Real-Time-IoT-Integrated-Piezoelectric-Power-System

A smart energy harvesting system that captures mechanical vibrations using piezoelectric transducers and sends real-time voltage, current, and power data to the cloud via **ESP32** and **Firebase**.

## 📌 Project Overview

This project presents an **IoT-enabled piezoelectric energy harvesting system** that converts mechanical pressure/vibrations into electrical energy, while also providing real-time performance monitoring via the cloud.


## 🔧 Problem Statement

Traditional piezoelectric systems lack visibility and diagnostic tools. This project overcomes those limitations by introducing:

- 📈 Real-time monitoring of voltage, current, and power.
- 🔍 Fault detection of piezoelectric elements via force sensors.
- ☁️ Live data streaming to Firebase Realtime Database.
- 📱 Mobile or Web dashboard integration for visualization.

## 🧠 Objectives

- Convert mechanical vibrations to electrical energy using **piezoelectric transducers**.
- Measure electrical parameters using **INA3221** sensor.
- Use **ESP32** for data acquisition and Wi-Fi-based cloud communication.
- Push data to **Firebase** for storage and remote access.
- Detect faulty transducers using **force sensors**.
- Provide live performance metrics on web/mobile dashboards.

## 🔁 System Workflow

Vibrations → Piezoelectric Transducer → Rectifier → INA3221 Sensor → ESP32 Microcontroller → Wi-Fi → Firebase RTDB → Web Dashboard

## 🧱 Architecture Diagram

[Vibrations]
↓
[Piezo Transducer]
↓
[Rectifier]
↓
[INA3221 Sensor] ← Force Sensor (for fault detection)
↓
[ESP32]
↓
[Wi-Fi Upload]
↓
[Firebase Database]
↓
[Mobile/Web Dashboard]

## 🛠️ Hardware Components

| Component              | Description                                      |
|------------------------|--------------------------------------------------|
| ESP32                  | Wi-Fi-enabled microcontroller for data handling  |
| INA3221                | 3-channel voltage/current/power sensor           |
| Piezoelectric Transducer | Converts vibration to electrical energy        |
| Force Sensor           | Detects faulty pressure responses                |
| Bridge Rectifier       | Converts AC to DC                                |
| Firebase               | Cloud storage (Realtime Database)                |
| NTP                    | Used for time synchronization                    |

## 🧪 Features

- 📶 Wireless data transmission using Wi-Fi
- 🧮 Measures voltage, current, and power across 3 channels
- 💾 Firebase integration for time-stamped history
- ⚠️ Fault detection mechanism
- 📊 Real-time data visualization on mobile/web apps
- 🔁 Expandable with more sensors/transducers

## 💻 Code Snippet

```cpp
float voltage_mv[3], current_ma[3], power_mw[3];
voltage_mv[i] = ina3221.getBusVoltage(i + 1) * 1000.0;
current_ma[i] = ina3221.getCurrentAmps(i + 1) * 1000.0;
power_mw[i]   = (voltage_mv[i] * current_ma[i]) / 1000.0;
Firebase.RTDB.setFloat(&fbdo, "/Channel1/History/timestamp/Voltage", voltage_mv[0]);


✅ Results
Metric	Value
Output Voltage (Avg)	~2.5 – 5V
Current (Peak)	Varies per load/channel
Power (Total)	Dynamic (based on input)
Fault Detection	Working (force sensor)
Cloud Storage	Firebase RTDB
Data Sync Interval	Every 5 seconds

🌍 Applications
🚗 Smart roads and bridges

🏭 Industrial vibration monitoring

🏃‍♂️ Wearable devices (shoes, bags)

🏢 Smart infrastructure health monitoring

🌆 Self-powered IoT nodes in smart cities

![image alt](https://github.com/roycedd/Real-Time-IoT-Integrated-Piezoelectric-Power-System/blob/de6ba5f3d5c6842b94146a1ca92e0fcee35f75f0/pictureee.png)
