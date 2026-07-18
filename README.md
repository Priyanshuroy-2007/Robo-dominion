# Robo-Dominion 🤖🎯

**Robo-Dominion** is a competitive robotic laser tag system built around Li-Fi technology. Developed as an independent event under the **Yantra Robotics Society** for IITM Paradox 2026, this project combines hardware engineering, signal processing, and low-latency networking to create a tactical bot combat experience.

## 🚀 Project Overview

Unlike traditional physical combat bots (Robosoccer/Sumo), Robo-Dominion bots engage in non-contact, precision laser tag. Bots fire laser signals at opponents, and hits are detected via onboard solar panel sensors. A centralized ESP-NOW master network monitors the arena, tracking health, handling shield regeneration logic, and updating real-time player statuses.

## ✨ Key Features

*   **Li-Fi Hit Detection:** Utilizes directed lasers and solar panel sensors for highly accurate, physical-contact-free hit registration.
*   **Real-Time Telemetry:** Operates on a robust **ESP-NOW** master network for low-latency, Wi-Fi-independent communication between the bots and the central game server.
*   **Dynamic Health & Combat System:** 
    *   Custom health degradation logic upon receiving a valid laser strike.
    *   Automatic shield/health regeneration mechanics that encourage tactical retreats and cover-based gameplay.
    *   Immediate visual health feedback via **WS2812 RGB LEDs**.
*   **Web Control Interface:** An integrated web server hosts the control UI, allowing players to manage motor movement, servo actuation, and monitor system health seamlessly from a browser.

## 🛠️ Hardware & Tech Stack

### Hardware
*   **Microcontrollers:** ESP-series (ESP32/ESP8266) for ESP-NOW and Web Server capabilities.
*   **Sensors/Receivers:** Mini solar panels for optical signal detection.
*   **Emitters:** Laser diode modules.
*   **Indicators:** WS2812 (NeoPixel) RGB LEDs.
*   **Actuators:** DC Motors (drive base) and Servos (aiming/mechanisms).

### Software
*   **Firmware:** C/C++ 
*   **Networking:** ESP-NOW protocol (Master/Slave mesh), HTTP Web Server for UI.
*   **Control Logic:** Custom hit-detection algorithms, health state machines, and motor PWM control.

## 🎮 Gameplay Mechanics

1.  **Engage:** Players navigate their bots using the web interface and aim their lasers at enemy solar panels.
2.  **Hit Registration:** When a laser hits a solar panel, the voltage differential is processed by the MCU as a hit. The bot's onboard logic immediately updates its health state and broadcasts this over the ESP-NOW network.
3.  **Visual Feedback:** The WS2812 LEDs instantly change color to reflect current health levels (e.g., Green ➔ Yellow ➔ Red).
4.  **Regeneration:** If a bot avoids taking damage for a set duration, the automatic shield regeneration logic kicks in, slowly restoring its health pool.

## 📅 Event Context

This hardware and control system was designed for deployment at **Paradox 2026** (ICSR Hall 4, IIT Madras) to demonstrate practical applications of hardware integration, signal processing, and mesh networking to faculty guests and participants.

---
*Developed under the Yantra Robotics Society, IITM BS.*
