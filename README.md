#  Smart Warm Air Regulator — Instrumentation Project

This repository contains the implementation and documentation for the **Instrumentation Project** at **Amirkabir University of Technology (AUT)**.  
The goal of this project is to design and build a **smart home warm air regulation system** capable of monitoring and adjusting ambient temperature using wireless communication and automated control.

---

##  Project Overview

###  Objective
To design and implement a **home warm air control device** that:
- Monitors the ambient temperature.
- Sends data wirelessly.
- Adjusts airflow direction and temperature setpoint automatically.
- Provides full wireless control via Bluetooth.

---

##  System Features

1. **Wireless Temperature Monitoring**
   - Reads ambient temperature using an **analog temperature sensor** (e.g., LM35, LM335).
   - Sends data wirelessly to a receiver (e.g., a smartphone or PC).
   - If using a digital sensor such as **DHT11/DHT22**, include its corresponding library and brief documentation.

2. **Temperature Regulation**
   - Maintains the ambient temperature within a **±5°C deadband** around the setpoint.
   - The heating unit is simulated using an LED indicator instead of a real heater.

3. **Adjustable Airflow Direction**
   - Controlled by a **DC motor (armature)** that adjusts the angle of the air outlet.
   - The motor can rotate **left or right** depending on control signals.

4. **Limit Switches**
   - Installed at both ends of the motor’s rotation range.
   - Automatically reverse the direction when triggered.

5. **Wireless Motor Control**
   - The motor’s rotation can also be **remotely controlled** via a Bluetooth connection.

6. **Wireless Setpoint Configuration**
   - The user can **set or modify the target temperature** wirelessly using a Bluetooth terminal app (e.g., *Bluetooth Serial Terminal* on Android).

7. **Expandable Design**
   - Additional logic or safety features (e.g., overheat protection, calibration routines, data logging) can be added for further improvement.

---

##  System Architecture

| Component | Description |
|------------|-------------|
| **Controller** | ESP32 microcontroller |
| **Temperature Sensor** | LM35 / LM335 (analog) or DHT11/DHT22 (digital) |
| **Wireless Communication** | Bluetooth Low Energy (BLE) |
| **Motor Control** | Dual-channel relay module with optocoupler |
| **Limit Switches** | Mechanical or capacitive switches |
| **Heater/Fan Simulation** | LEDs representing system states |

---

##  Wireless Communication

- Communication is established using **Bluetooth Low Energy (BLE)**.
- Data can be sent and received through the **Bluetooth Serial Terminal** Android app.
- The ESP32 receives commands such as:
  - Setting the desired temperature.
  - Manually starting or stopping the motor.
  - Requesting current temperature data.

---

##  Control Logic Summary

- Read ambient temperature.
- Compare with the setpoint ±5°C band.
- If temperature < (setpoint - 5): activate heater LED (simulate warm air output).
- If temperature > (setpoint + 5): deactivate heater LED.
- Continuously adjust motor direction with feedback from limit switches.
- Update and transmit current temperature over Bluetooth.

---

##  Tools & Environment

- **Microcontroller:** ESP32  
- **Programming Platform:** Arduino IDE  
- **Sensors:** LM35 / DHT11  
- **Communication:** Bluetooth (BLE)  
- **Motor Driver:** 2-channel relay module  
- **Language:** C / Arduino

##  Demo

A demo video of the project operation, including wireless temperature monitoring and motor control, is available in:  
 `demo/project_demo.mp4`

---

##  Author
**Setayesh Khasehtarash**  
Instrumentation Project — Amirkabir University of Technology  

---

##  License
This project is provided for educational purposes as part of the Instrumentation coursework at AUT.


