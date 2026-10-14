# IEEE RAS Task 2: Distance Alert System

An automated **Distance Alert System** designed to detect incoming obstacles in real time and trigger instant visual and audio safety warnings. This repository contains the architecture, schematics, and Arduino firmware implementation for the project.

## 🚀 Overview
The system utilizes an ultrasonic sensor to monitor front-facing proximity boundaries. When an object breaches the predefined safety zone, a microcontroller handles the wave travel delays and immediately actuates localized alerts to prevent collisions.

### Key Features
* **Real-time Proximity Tracking:** High-frequency sonic wave ping processing.
* **Dual Alert System:** Simultaneous active visual (LED) and auditory (Piezo Buzzer) indicators.
* **Configurable Perimeter:** Dynamic safety thresholds adjustable directly via firmware constraints.
* **Interactive Simulation:** Fully testable virtual prototype available on Tinkercad.

---

## 🔗 Interactive Simulation & Resource
You can access, fork, and run the live interactive circuit simulation directly through the project's [Tinkercad Dashboard](https://www.tinkercad.com/things/1Cw8P5l4FDG-ieee-ras-task-2-distance-alert-system "Tinkercad Distance Alert System Link").

---

## 🛠️ Hardware Components
* **Microcontroller:** Arduino Uno (or Nano)
* **Sensor:** HC-SR04 Ultrasonic Sensor
* **Visual Alert:** 5V Red LED + 220Ω Resistor
* **Audio Alert:** 5V Piezo Buzzer
* **Prototyping:** Breadboard and M-M Jumper wires

---

## 🔌 Circuit Wiring Architecture

| HC-SR04 Sensor | Arduino Pin | Alert Actuators | Arduino Pin |
| :--- | :--- | :--- | :--- |
| **VCC** | 5V | **LED (+)** | Pin 12 (via Resistor) |
| **GND** | GND | **Buzzer (+)** | Pin 11 |
| **Trig** | Pin 9 | **Common Ground (-)** | GND |
| **Echo** | Pin 10 | | |

---

## 💻 Logic Flow
1. **Triggering:** The Arduino fires a high-frequency 10µs pulse through the sensor's transmitter.
2. **Calculation:** The receiver catches the bounced echo. Distance is calculated using the speed of sound:  
   $$\text{Distance (cm)} = \frac{\text{Duration} \times 0.034}{2}$$
3. **Evaluation:** If the returned target distance crosses below the **20 cm safety threshold**, the alert loop triggers.

---

## 🛠️ Getting Started

### Prerequisites
* [Arduino IDE](https://www.arduino.cc/en/software "Arduino Download Page") installed on your system.

### Installation & Flashing
1. **Clone the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/ieee-ras-distance-alert.git
   ```
2. Open the `.ino` sketch file in your Arduino IDE.
3. Select your target board (**Tools > Board > Arduino Uno**).
4. Match your active COM port (**Tools > Port**).
5. Click **Upload** to flash the code onto your hardware.
6. Open your **Serial Monitor** at `9600 baud` to view active distance telemetry calibrations.
