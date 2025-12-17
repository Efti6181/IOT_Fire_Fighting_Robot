# 🚒 IoT Fire-Fighting Robot (ESP32 Based)

An advanced **IoT fire-fighting and safety robot** built using ESP32, flame sensors, gas sensor, temperature/humidity sensors, servo-controlled water extinguisher, mist maker, fan, and full 4WD motor chassis.
The robot can **detect fire, smoke/gas, high temperature, high humidity, obstacles** and automatically respond, along with full **manual control over WiFi**.

---

## 🔥 Features

### **🔥 Fire Detection & Water Extinguish System**

* 3 Flame sensors: **Left, Middle, Right**
* Robot moves toward the fire direction
* Auto activates:

  * Red LED
  * Buzzer
  * Water Pump
  * **Servo sweeps 0°–90° (4 times)** to spray water

### **🧪 Gas Detection (MQ-2)**

* Detects gas/smoke
* Runs **Fan for 10 seconds**
* Green LED ON
* Buzzer active

### **🌡 Temperature & Humidity Control**

* 2× DHT11 sensors
* If:

  * **Temperature ≥ 40°C**, or
  * **Humidity ≥ 80%**
* **Mist maker** turns ON to reduce heat/humidity

### **🚧 Obstacle Detection**

* Ultrasonic sensor (HC-SR04)
* If object ≤ **5 cm** → Buzzer gives **pip-pip** alert

### **🎮 Manual RC-Style Control**

* Web dashboard allows:

  * Forward / Backward / Left / Right
  * Pump ON/OFF
  * Fan ON/OFF
  * Mist Maker ON/OFF
  * Real-time sensor reading

### **📡 WiFi + Offline Website**

* ESP32 creates its **own WiFi hotspot (AP Mode)**
* Custom local webpage hosted on ESP32
* Works **completely offline**
* Shows:

  * Temperature
  * Humidity
  * Distance
  * Fire status
  * Gas status
  * Pump/Fan/Mist/LED/Servo status

---

## 🛠 Hardware Used

| Component                  | Qty |
| -------------------------- | --- |
| ESP32                      | 2   |
| 4WD Motor Chassis          | 1   |
| L298N Motor Driver         | 1   |
| Flame Sensor               | 3   |
| DHT11 Sensor               | 2   |
| MQ-2 Gas Sensor            | 1   |
| Ultrasonic HC-SR04         | 1   |
| Servo Motor                | 1   |
| 2-Channel Relay            | 1   |
| 1-Channel Relay            | 1   |
| DC-DC Buck Converter       | 1   |
| 3× 3.7V Battery Pack (12V) | 1   |
| 2× 3.7V Battery Pack (8V)  | 1   |
| Water Pump (5V)            | 1   |
| Fan                        | 1   |
| Mist Maker                 | 1   |
| Buzzer                     | 2   |
| Green LED                  | 1   |
| Red LED                    | 1   |

---

## 🔌 System Design (Block Diagram)

<img width="572" height="623" alt="image" src="https://github.com/user-attachments/assets/9358d81b-38cb-4981-be7d-fb1cec92b746" />



## 📡 Connectivity

* Robot creates a WiFi hotspot using ESP32 (AP Mode)
* User connects via phone or laptop
* Website works offline
* Control + real-time monitoring supported

---

## 🌐 Web Dashboard

### **Displays:**

* Temperature
* Humidity
* Ultrasonic Distance
* Fire Detected?
* Gas Detected?
* Pump Status
* Fan Status
* Mist Maker Status
* Servo Status
* LED + Buzzer states

### **Controls:**

* Manual movement (Forward/Back/Left/Right)
* Pump ON/OFF
* Fan ON/OFF
* Mist Maker ON/OFF
* Servo toggle

---

## 🧠 Working Logic (Summary)

| Event                        | Robot Action                                         |
| ---------------------------- | ---------------------------------------------------- |
| Left Flame Detected          | Turn left + red LED + buzzer + pump + servo spray    |
| Middle Flame Detected        | Move forward + red LED + buzzer + pump + servo spray |
| Right Flame Detected         | Turn right + red LED + buzzer + pump + servo spray   |
| MQ-2 Gas Detected            | Fan ON 10s + green LED + buzzer                      |
| Temp ≥ 40°C / Humidity ≥ 80% | Mist Maker ON                                        |
| Obstacle ≤ 5 cm              | Buzzer pip-pip                                       |
| Manual Web Input             | RC-style movement + device control                   |

---




## 🧪 Testing Checklist

* [ ] Flame detection working (L/M/R)
* [ ] Servo + pump spraying correct
* [ ] Gas detection triggers fan
* [ ] Mist maker starts at high temp/humidity
* [ ] Ultrasonic distance correct
* [ ] Chassis movement correct
* [ ] Website loads offline
* [ ] All manual ON/OFF controls working

---

## 📷 Photos 

<p align="center">
  <img src="https://github.com/user-attachments/assets/18ba8220-5734-4624-b505-38ef4cd53c77" width="300">
  <img src="https://github.com/user-attachments/assets/d5fd023d-1a18-4970-bcd1-644ca4b9a8c7" width="300">
  <img src="https://github.com/user-attachments/assets/11316b26-3c52-4d9f-a821-f81a0709ecfd" width="300">
</p>

## 📷 Web App

<img width="757" height="717" alt="image" src="https://github.com/user-attachments/assets/877ecc76-7ea3-4fac-81c6-39742a437253" />


---


## 📜 License

This project is licensed under the ![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)  

---

## 👨‍💻 Author

**Najmul Alam Efti**

🎓 Premier University, Chittagong

📧 \[najmul27alam@gmail.com]


