# Vaskos
BLARE V2 — 3-Switch Macropad & Alarm Clock
A custom 3-switch Cherry MX macropad and alarm clock built with the Seeeduino XIAO ESP32-C3 for the Hack Club BLARE initiative.

Overview
BLARE V2 is an open-source hardware project designed to function both as a desktop macropad and a programmable alarm clock. It features three mechanical key switches, an integrated buzzer for audio notifications, and a dedicated interface header for an external display module.

Technical Specifications
Microcontroller: Seeed Studio XIAO ESP32-C3

Inputs: 3× Cherry MX mechanical switches (Push buttons)

Audio Output: Integrated active/passive buzzer

Display Interface: 8-pin header (SPI display support)

Power & Connectivity: USB-C via XIAO ESP32-C3

Form Factor: Custom 2-layer PCB with rounded Edge.Cuts corners and M3 symmetric mounting holes

Hardware & PCB Features
Dual-Layer Routing: 100% routed traces on Top and Bottom layers with optimized via placement.

USB-C Accessibility: Positioned with proper connector clearance extending beyond the board perimeter.

Display Mounting: Inline pin header footprint designed for direct screen mounting without loose jumper wires.

Grounding: Solid copper ground plane (GND fill) across unused PCB areas for reduced noise and reliable operation.

Project Structure
Plaintext
├── hardware/
│   ├── blare_v2.kicad_sch    # Main KiCad schematic
│   ├── blare_v2.kicad_pcb    # PCB layout file
│   └── gerbers/              # Production Gerber & Drill files
└── README.md
Getting Started
Clone the repository:

Bash
git clone https://github.com/your-username/blare-v2.git
Open blare_v2.kicad_pro in KiCad 7.0+ to view or modify the schematic and PCB layout.

Review the Gerber files in /gerbers for PCB manufacturing.
