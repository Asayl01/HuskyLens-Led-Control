# HuskyLens with Arduino

## Project Idea

The goal is to control the color of a single RGB LED using color detection. When the HuskyLens detects a specific color, the Arduino will light up the corresponding color in the RGB LED:
- Red color → Red light
- Green color → Green light
- Blue color → Blue light

---

## Components Needed

- HuskyLens AI Camera
- Arduino Uno (or similar)
- 1 RGB LED (Common Anode)
- 3 Resistors (220Ω)
- Jumper Wires
- Breadboard
- USB Cable (for power and programming)

---

## What is HuskyLens?

HuskyLens is an AI vision sensor that can detect and recognize faces, objects, colors, lines, and tags using built-in machine learning. It’s easy to use and integrates with Arduino, Raspberry Pi, and other microcontrollers via I2C or UART. It also features a built-in display for real-time visual feedback.

![HuskyLens](Huskylens.jpg)

---

## Features

- **Color Recognition** – Detects and identifies trained colors.
- **Face Recognition** – Learns and recognizes human faces.
- **Object Recognition** – Identifies custom trained objects.
- **Object Classification** – Categorizes items into classes.
- **Object Tracking** – Follows moving objects automatically.
- **Line Tracking** – Tracks lines for robotics applications.
- **Tag Recognition (AprilTag)** – Reads visual markers like tags and IDs.

---

## Applications

- Robotics and smart vehicle navigation  
- Face-based entry or security systems  
- Color-triggered lighting or actions  
- Vision-based object interaction  
- Educational AI learning kits  
- IoT systems with visual input

---

## RGB LED Overview

In this project, we use a **Common Anode RGB LED**, which has:

- One common positive (anode) pin connected to 5V
- Three separate pins for Red, Green, and Blue cathodes connected to Arduino pins via 220Ω resistors
- To turn on a color, the corresponding Arduino pin is set **LOW** (because the LED is common anode)

| Color | Arduino Pin |
|-------|-------------|
| Red   | D7          |
| Green | D9          |
| Blue  | D8          |

---

## How to Install the HuskyLens Library

### Method 1: From Arduino IDE

1. Go to **Sketch > Include Library > Manage Libraries...**  
2. Search for **HuskyLens**  
3. Click **Install**

### Method 2: Manual Installation

1. Download the library from this link:  
   [Download HuskyLens Library](https://wiki.dfrobot.com/HUSKYLENS_V1.0_SKU_SEN0305_SEN0336#4.%20Upgrade%20Firmware)  
2. Extract the ZIP file  
3. Move the folder to: `Documents/Arduino/libraries`

---

## HuskyLens to Arduino Wiring

| HuskyLens Pin | Arduino Pin |
|---------------|-------------|
| VCC           | 5V          |
| GND           | GND         |
| TX            | A4 (SDA)    |
| RX            | A5 (SCL)    |

> 💡 Note: The default communication protocol is I2C. For Arduino Uno, use A4 (SDA) and A5 (SCL).

---

## Wiring Diagram

![Wiring Diagram](huskylens-ardiono-i2c.png)
