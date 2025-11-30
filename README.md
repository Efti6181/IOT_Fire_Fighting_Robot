Here is an **even more polished, premium-quality GitHub README**, written in a clean, professional style — perfect for showcasing your project.
You can **copy–paste directly** into GitHub with no changes needed.

---

# 🔥🤖 IoT-Based Autonomous Fire-Fighting & Environmental Monitoring Robot

*A complete multi-hazard safety robot with fire detection, gas sensing, environmental monitoring, autonomous movement, and IoT control — powered by ESP32.*

---

## 📘 **Introduction**

This project presents an **IoT-enabled autonomous fire-fighting robot** capable of detecting fire, harmful gases, temperature rise, humidity imbalance, and nearby obstacles.
Using dual ESP32 microcontrollers, multiple sensors, relays, and a servo-based water spray system, the robot can **locate fire direction automatically**, extinguish it using a water pump, and provide **real-time monitoring** through a web dashboard — even **offline**, without internet.

Designed for safety, low cost, and accessibility, this system is ideal for **homes, small industries, workshops, and rural areas**.

---

## 🚀 **Key Features**

### 🔥 Fire Detection & Extinguishing

* 3 flame sensors (Left, Middle, Right) detect fire direction.
* Robot automatically moves toward the fire.
* Water pump activated to spray water.
* Servo rotates 0°→90° four times to cover a wider area.
* Red LED + buzzer activated during fire mode.

### 🏭 Gas Detection (MQ-2)

* Detects smoke, LPG, methane & general hazardous gas.
* Automatically turns on fan for 10 seconds.
* Green LED + buzzer alert.

### 🌡 Temperature & Humidity Control

* Dual DHT11 sensors monitor environment.
* If **Temp > 40°C** or **Humidity > 80%** → Mist maker activates.
* Helps reduce heat and maintain safe humidity levels.

### 🚧 Obstacle Detection

* Ultrasonic sensor detects objects within **5 cm**.
* Buzzer gives “pip-pip” warning for collision prevention.

### 🌐 Offline IoT Control (No Internet Needed)

* ESP32 creates its own Wi-Fi hotspot.
* Connect via phone/laptop browser.
* Control robot like an RC car: Forward/Back/Left/Right/Stop.
* Manually control pump, fan, mist maker.
* View **real-time**:

  * Temperature
  * Humidity
  * Distance
  * Flame status
  * Gas status
  * Device on/off indicators

---

## 🛠️ **Hardware Components**

* **ESP32 (x2)**
* **4WD Chassis + DC Motors**
* **L298N Motor Driver**
* **Flame Sensors (x3)**
* **DHT11 Sensors (x2)**
* **MQ-2 Gas Sensor**
* **Ultrasonic Sensor**
* **Servo Motor**
* **5V Water Pump**
* **Cooling Fan**
* **Mist Maker**
* **Two-Channel Relay**
* **One-Channel Relay**
* **DC-DC Buck Converter**
* **Li-ion Battery Packs (2-cell & 3-cell)**
* **Buzzers (x2)**
* **Green & Red LED**

---

## ⚙️ **System Architecture**

```
                 ┌──────── Flame Sensors ────────┐
                 │                                │
      [ESP32 #1] ─── Motor Driver ─── 4WD Drive   │
                 │                                │
                 └──── Water Pump + Servo ────────┘


                 ┌──────── DHT11 Sensors ─────────┐
                 │                                │
                 ├──────── MQ-2 Gas Sensor ───────┤
      [ESP32 #2]─┤                                ├── Web Dashboard (AP Mode)
                 ├──── Ultrasonic Sensor ─────────┤
                 │                                │
                 └─ Fan, Mist Maker, LEDs, Buzzers┘
```

---

## 🧩 **How the Robot Works**

### 🟥 Fire Mode

| Flame Detected | Robot Movement | Actions                                    |
| -------------- | -------------- | ------------------------------------------ |
| Left           | Turn left      | Pump ON, Servo sweeps, Buzzer + Red LED ON |
| Middle         | Move forward   | Same actions                               |
| Right          | Turn right     | Same actions                               |

### 🟩 Gas Mode (MQ-2)

* Fan ON (10s)
* Green LED ON
* Buzzer alert

### 🟦 Temperature/Humidity Mode

* Temp > 40°C OR Humidity > 80% → Mist maker ON

### 🟨 Obstacle Mode

* Distance ≤ 5 cm → Buzzer “pip-pip”

### 🟧 Manual IoT Mode

* Web dashboard RC control
* Manual switching of pump, fan, mist maker
* Live sensor feedback

---

## 🧪 **Results**

* Accurate directional fire detection and movement.
* Quick response to gas leaks.
* Mist maker effectively lowers temperature/humidity.
* Stable 4WD motion with good traction.
* Web UI updates instantly with no internet required.
* Successfully extinguished real test flames.

---

## ⚠️ **Errors & Limitations**

* Water spray accuracy affected by wind.
* Wi-Fi hotspot range limited (depends on ESP32 power).
* Battery drains fast during heavy use (pump + fan).
* Servo slows when battery voltage drops.
* MQ-2 accuracy affected by humidity.
* Ultrasonic sensor gives incorrect values on soft/angled surfaces.
* Pump pressure decreases when water level is low.
* Continuous use requires frequent recharging.

---

## 🌱 **Impact Assessment**

### **Health & Safety**

* Prevents fire spread and reduces life risk.
* Detects harmful gases early.
* Automates hazardous tasks, keeping humans safe.

### **Societal**

* Low-cost disaster-prevention tool.
* Beneficial for rural homes, small shops, and workshops.
* Enhances awareness of home safety.

### **Environmental**

* Uses **water**, not chemicals.
* Rechargeable batteries reduce waste.
* Low-power sensors save energy.

### **Economic**

* Built using affordable components.
* Reduces property loss from fires.
* Easy to maintain and repair.

### **Ethical**

* Promotes responsible engineering design.
* Avoids any harmful surveillance features.
* Uses transparent, sensor-based decisions.

### **Teamwork & Learning**

* Improved coding, web development, electronics, and robotics skills.
* Learned problem-solving, debugging, and system integration.

---

## 📁 **Repository Structure**

```
📂 FireFighting-Robot/
│── src/
│── web-dashboard/
│── circuits/
│── images/
│── README.md
│── LICENSE
```

---

## ▶️ **How to Use**

1. Upload code to both ESP32 boards.
2. Assemble hardware as per the circuit diagram.
3. Power the system:

   * 12V battery → L298N
   * 8V battery → Buck converter → ESP32 + sensors
4. Connect to ESP32 hotspot:

   ```
   SSID: FireFighter_AP
   Password: 12345678
   ```
5. Open the IP shown in Serial Monitor.
6. Control robot + view live data.

---

## 📸 **Project Photos & Demo**

*(Add images here)*

---

## 🔮 **Future Improvements**

* AI-based fire classification (ESP32-CAM)
* Fire-resistant chassis
* Stronger water spray
* Android/iOS App
* Fully autonomous navigation

---

## 👤 **Author**

**Najmul Alam Efti**
IoT & Robotics Developer

---

## ⭐ **Support the Project**

If you found this project useful, please consider giving the repository a **⭐Star**!

---

If you want, sir, I can also:
✅ Add GitHub badges (Release, License, Hardware Used, Made with ❤️ etc.)
✅ Create a project banner/header
Just tell me!
Here is an **even more polished, premium-quality GitHub README**, written in a clean, professional style — perfect for showcasing your project.
You can **copy–paste directly** into GitHub with no changes needed.

---

# 🔥🤖 IoT-Based Autonomous Fire-Fighting & Environmental Monitoring Robot

*A complete multi-hazard safety robot with fire detection, gas sensing, environmental monitoring, autonomous movement, and IoT control — powered by ESP32.*

---

## 📘 **Introduction**

This project presents an **IoT-enabled autonomous fire-fighting robot** capable of detecting fire, harmful gases, temperature rise, humidity imbalance, and nearby obstacles.
Using dual ESP32 microcontrollers, multiple sensors, relays, and a servo-based water spray system, the robot can **locate fire direction automatically**, extinguish it using a water pump, and provide **real-time monitoring** through a web dashboard — even **offline**, without internet.

Designed for safety, low cost, and accessibility, this system is ideal for **homes, small industries, workshops, and rural areas**.

---

## 🚀 **Key Features**

### 🔥 Fire Detection & Extinguishing

* 3 flame sensors (Left, Middle, Right) detect fire direction.
* Robot automatically moves toward the fire.
* Water pump activated to spray water.
* Servo rotates 0°→90° four times to cover a wider area.
* Red LED + buzzer activated during fire mode.

### 🏭 Gas Detection (MQ-2)

* Detects smoke, LPG, methane & general hazardous gas.
* Automatically turns on fan for 10 seconds.
* Green LED + buzzer alert.

### 🌡 Temperature & Humidity Control

* Dual DHT11 sensors monitor environment.
* If **Temp > 40°C** or **Humidity > 80%** → Mist maker activates.
* Helps reduce heat and maintain safe humidity levels.

### 🚧 Obstacle Detection

* Ultrasonic sensor detects objects within **5 cm**.
* Buzzer gives “pip-pip” warning for collision prevention.

### 🌐 Offline IoT Control (No Internet Needed)

* ESP32 creates its own Wi-Fi hotspot.
* Connect via phone/laptop browser.
* Control robot like an RC car: Forward/Back/Left/Right/Stop.
* Manually control pump, fan, mist maker.
* View **real-time**:

  * Temperature
  * Humidity
  * Distance
  * Flame status
  * Gas status
  * Device on/off indicators

---

## 🛠️ **Hardware Components**

* **ESP32 (x2)**
* **4WD Chassis + DC Motors**
* **L298N Motor Driver**
* **Flame Sensors (x3)**
* **DHT11 Sensors (x2)**
* **MQ-2 Gas Sensor**
* **Ultrasonic Sensor**
* **Servo Motor**
* **5V Water Pump**
* **Cooling Fan**
* **Mist Maker**
* **Two-Channel Relay**
* **One-Channel Relay**
* **DC-DC Buck Converter**
* **Li-ion Battery Packs (2-cell & 3-cell)**
* **Buzzers (x2)**
* **Green & Red LED**

---

## ⚙️ **System Architecture**

```
                 ┌──────── Flame Sensors ────────┐
                 │                                │
      [ESP32 #1] ─── Motor Driver ─── 4WD Drive   │
                 │                                │
                 └──── Water Pump + Servo ────────┘


                 ┌──────── DHT11 Sensors ─────────┐
                 │                                │
                 ├──────── MQ-2 Gas Sensor ───────┤
      [ESP32 #2]─┤                                ├── Web Dashboard (AP Mode)
                 ├──── Ultrasonic Sensor ─────────┤
                 │                                │
                 └─ Fan, Mist Maker, LEDs, Buzzers┘
```

---

## 🧩 **How the Robot Works**

### 🟥 Fire Mode

| Flame Detected | Robot Movement | Actions                                    |
| -------------- | -------------- | ------------------------------------------ |
| Left           | Turn left      | Pump ON, Servo sweeps, Buzzer + Red LED ON |
| Middle         | Move forward   | Same actions                               |
| Right          | Turn right     | Same actions                               |

### 🟩 Gas Mode (MQ-2)

* Fan ON (10s)
* Green LED ON
* Buzzer alert

### 🟦 Temperature/Humidity Mode

* Temp > 40°C OR Humidity > 80% → Mist maker ON

### 🟨 Obstacle Mode

* Distance ≤ 5 cm → Buzzer “pip-pip”

### 🟧 Manual IoT Mode

* Web dashboard RC control
* Manual switching of pump, fan, mist maker
* Live sensor feedback

---

## 🧪 **Results**

* Accurate directional fire detection and movement.
* Quick response to gas leaks.
* Mist maker effectively lowers temperature/humidity.
* Stable 4WD motion with good traction.
* Web UI updates instantly with no internet required.
* Successfully extinguished real test flames.

---

## ⚠️ **Errors & Limitations**

* Water spray accuracy affected by wind.
* Wi-Fi hotspot range limited (depends on ESP32 power).
* Battery drains fast during heavy use (pump + fan).
* Servo slows when battery voltage drops.
* MQ-2 accuracy affected by humidity.
* Ultrasonic sensor gives incorrect values on soft/angled surfaces.
* Pump pressure decreases when water level is low.
* Continuous use requires frequent recharging.

---

## 🌱 **Impact Assessment**

### **Health & Safety**

* Prevents fire spread and reduces life risk.
* Detects harmful gases early.
* Automates hazardous tasks, keeping humans safe.

### **Societal**

* Low-cost disaster-prevention tool.
* Beneficial for rural homes, small shops, and workshops.
* Enhances awareness of home safety.

### **Environmental**

* Uses **water**, not chemicals.
* Rechargeable batteries reduce waste.
* Low-power sensors save energy.

### **Economic**

* Built using affordable components.
* Reduces property loss from fires.
* Easy to maintain and repair.

### **Ethical**

* Promotes responsible engineering design.
* Avoids any harmful surveillance features.
* Uses transparent, sensor-based decisions.

### **Teamwork & Learning**

* Improved coding, web development, electronics, and robotics skills.
* Learned problem-solving, debugging, and system integration.

---

## 📁 **Repository Structure**

```
📂 FireFighting-Robot/
│── src/
│── web-dashboard/
│── circuits/
│── images/
│── README.md
│── LICENSE
```

---

## ▶️ **How to Use**

1. Upload code to both ESP32 boards.
2. Assemble hardware as per the circuit diagram.
3. Power the system:

   * 12V battery → L298N
   * 8V battery → Buck converter → ESP32 + sensors
4. Connect to ESP32 hotspot:

   ```
   SSID: FireFighter_AP
   Password: 12345678
   ```
5. Open the IP shown in Serial Monitor.
6. Control robot + view live data.

---

## 📸 **Project Photos & Demo**

*(Add images here)*

---

## 🔮 **Future Improvements**

* AI-based fire classification (ESP32-CAM)
* Fire-resistant chassis
* Stronger water spray
* Android/iOS App
* Fully autonomous navigation

---

## 👤 **Author**

**Najmul Alam Efti**
IoT & Robotics Developer

---

## ⭐ **Support the Project**

If you found this project useful, please consider giving the repository a **⭐Star**!

---

If you want, sir, I can also:
✅ Add GitHub badges (Release, License, Hardware Used, Made with ❤️ etc.)
✅ Create a project banner/header
Just tell me!
