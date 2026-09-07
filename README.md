#  Vaskos — Custom Desktop Alarm Clock & Macropad

[![Platform: BLARE](https://img.shields.io/badge/Platform-BLARE%20%28Hack%20Club%20STARDANCE%29-ff69b4.svg)](https://blare.hackclub.com)
[![Status: In Progress](https://img.shields.io/badge/Status-In%20Progress-yellow.svg)](#)
[![Level: Intermediate](https://img.shields.io/badge/Level-Intermediate-blue.svg)](#)

**Vaskos** is an open-source, angled desktop alarm clock and productiveness timer built for the **BLARE** initiative by Hack Club. It features an integrated 3x3 mechanical keypad (macropad), a retro 8-bit alarm system, and an optimized hardware footprint powered by the Seeed Studio XIAO ESP32C3.

---

##  Key Features

- **Puzzle Alarm:** Deactivate the morning alarm by completing button sequences or solving quick visual prompts.
- **Focus Timer:** Functions as a desktop Pomodoro timer during work hours.
- **Retro Audio Feedback:** Custom 8-bit sound effects via a 3.3V piezo buzzer.
- **Ergonomic Design:** 45-degree angled 3D-printed enclosure secured with M3 heat-set inserts.

---

##  Hardware Requirements & Bill of Materials

| Component | Qty | Description / Pin Connection |
| :--- | :---: | :--- |
| **Seeed Studio XIAO ESP32C3** | 1 | Microcontroller (11 Available GPIOs) |
| **2.25″ TFT Display** | 1 | SPI Interface for clock UI & timers |
| **Cherry MX Switches** | 9 | Configured in a 3x3 Key Matrix |
| **1N4148 Diodes** | 9 | Matrix ghosting prevention |
| **3.3V Active/Passive Buzzer** | 1 | Audio feedback & alarm tones |
| **3D Printed Enclosure** | 1 | Angled desktop housing with M3 inserts |

---

##  GPIO Pin Budgeting (11 Pins Total)

To fit all features onto the 11 GPIO pins of the XIAO ESP32C3, hardware pin-saving optimizations are implemented for the display:

###  Display Optimization (4 GPIOs)
* `GND` $\rightarrow$ **GND**
* `VCC` $\rightarrow$ **3.3V**
* `BL` (Backlight) $\rightarrow$ **GND** *(Hardwired always-on)*
* `RST` (Reset) $\rightarrow$ **3.3V** *(Hardwired to save 1 pin)*
* `SCL` / `SDA` / `DC` / `CS` $\rightarrow$ **4 Dedicated GPIO Pins**

###  Audio & ⌨️ 3x3 Key Matrix (7 GPIOs)
* **Buzzer:** 1 PWM GPIO Pin
* **Matrix Rows (3):** 3 Output GPIO Pins
* **Matrix Columns (3):** 3 Input GPIO Pins (with internal pull-up/down)

---

##  Project Structure

```text
.
├── CAD/              # 3D models and STL files for the enclosure
├── Hardware/         # KiCad schematics and PCB layout files
├── Firmware/         # Arduino / C++ source code
└── README.md         # Project documentation
