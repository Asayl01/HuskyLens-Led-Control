# HuskyLens With RGB LED 

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

An RGB LED combines Red, Green, and Blue LEDs in one package, allowing you to create various colors by mixing these three basic colors.

### How It Works

- Each color pin (Red, Green, Blue) connects to Arduino pins via 220Ω resistors.  
- For a **Common Anode** RGB LED, the common pin is connected to 5V.  
- The LED colors turn on when the corresponding Arduino pin is set to **LOW**.  
- By adjusting the brightness of each color using PWM (`analogWrite`), you can create a wide range of colors.

https://private-user-images.githubusercontent.com/210694101/465806556-b78c0ebf-ff08-4cdf-bbb7-ee658e4cfc84.MOV?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTI0NTczNDMsIm5iZiI6MTc1MjQ1NzA0MywicGF0aCI6Ii8yMTA2OTQxMDEvNDY1ODA2NTU2LWI3OGMwZWJmLWZmMDgtNGNkZi1iYmI3LWVlNjU4ZTRjZmM4NC5NT1Y_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNzE0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDcxNFQwMTM3MjNaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jYmY2ZTViMmViMzE4OWRiODE0MjBlM2U3YWU4NjJkNWIyNzA3ZDQwOTk0Zjc5NzM5YThkMTdhY2M1NWY3N2Q0JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.nqtLZygssm6YzpdNqHJY6iPBa5Hp2ZDh3-HeZ5hnYVA


For more details and to explore RGB color values, visit:  
[W3Schools RGB Colors Guide](https://www.w3schools.com/colors/colors_rgb.asp)

### Wiring to Arduino

![Wiring](2D_Circuit_Arduino-RGB-LED-common-anode.png)

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

> _Note: The default communication protocol is I2C. For Arduino Uno, use A4 (SDA) and A5 (SCL)._
> To change the communication protocol on HuskyLens, go to **Settings > Protocol Type**, select the desired protocol (e.g., I2C or UART), and then **Save** your changes.  
---

## Wiring Diagram

![Wiring Diagram](huskylens-ardiono-i2c.png)

---

## Complete Project Overview - Wiring 
| Component          | Pin on Component   | Connected to Arduino Pin | Notes                      |
|--------------------|--------------------|-------------------------|----------------------------|
| HuskyLens VCC      | VCC                | 5V                      | Power                      |
| HuskyLens GND      | GND                | GND                     | Ground                     |
| HuskyLens TX       | TX                 | A4 (SDA)                | I2C Data Line              |
| HuskyLens RX       | RX                 | A5 (SCL)                | I2C Clock Line             |
| RGB LED Common Anode| Common (+)          | 5V                      | Common positive pin        |
| RGB LED Red        | Red Pin            | 9                       | Connect via 220Ω resistor  |
| RGB LED Green      | Green Pin          | 8                       | Connect via 220Ω resistor  |
| RGB LED Blue       | Blue Pin           | 7                       | Connect via 220Ω resistor  |

## Project Result
This video shows the final result of the project — the RGB LED changing colors based on HuskyLens color recognition.

https://private-user-images.githubusercontent.com/210694101/465808530-b722f33b-a605-4dcf-9bf6-3bfab7212065.MOV?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTI0NTg5NDgsIm5iZiI6MTc1MjQ1ODY0OCwicGF0aCI6Ii8yMTA2OTQxMDEvNDY1ODA4NTMwLWI3MjJmMzNiLWE2MDUtNGRjZi05YmY2LTNiZmFiNzIxMjA2NS5NT1Y_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNzE0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDcxNFQwMjA0MDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT00NWVkYzlkOTk4NzM4MGEwN2ZhZGRmNzA2NmM5MzIyNjFjM2M2MTQxZjA1ZGM0NmM4MmM3MzU2MjNiMWFkNjdjJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.xWbITB98hzA1mpX-txue4w8X17VmUgyTrM19FB5m-6E

---

## Arduino Code

The full Arduino sketch used in this project is available in this repository:  
[`husky_rgb_led.ino`](Code.ino)



