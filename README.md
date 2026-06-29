# CANBUS Sniffer
**Version:** V1.0.0

A four-layer STM32-based CAN bus sniffer designed as an end-to-end PCB design project to demonstrate professional hardware development practices. This project emphasizes PCB layout, signal integrity, power integrity, USB routing, CAN bus design, and manufacturability.

![PCB Layout](images/pcb_layout.png)

![3D Render](images/pcb_3d.png)

---

# Project Goals

The purpose of this project was to:

- Design a complete embedded hardware system from schematic to PCB.
- Practice professional PCB layout techniques.
- Learn USB 2.0 differential pair routing.
- Learn CAN bus hardware design.
- Implement proper power distribution and filtering.
- Practice Design for Manufacturability (DFM).
- Practice Design for Assembly (DFA).
- Build a portfolio-quality PCB project.

---

# Features

- STM32F042 Microcontroller
- USB Type-C Interface
- CAN Bus Transceiver
- 5V USB Powered
- 3.3V Linear Regulation
- USB ESD Protection
- CAN Bus Termination Header
- SWD Programming Header
- Reset Pushbutton
- BOOT0 Pushbutton
- Four Mounting Holes
- Four-Layer PCB

---

# Board Specifications

| Parameter | Value |
|-----------|--------|
| PCB Layers | 4 |
| Layer Stack | Signal / GND / GND / Signal |
| Copper Weight | 1 oz |
| USB | USB Type-C (USB 2.0 FS) |
| MCU Supply | 3.3V |
| Input Supply | 5V USB |
| Communication | CAN Bus |
| Programming | SWD |

---

# Hardware Overview

## Microcontroller

STM32F042 series ARM Cortex-M0 MCU

Responsibilities:

- USB Device Interface
- CAN Communication
- Firmware Execution
- SWD Debugging

---

## USB Interface

USB Type-C connector

Features:

- CC1 / CC2 pull-down resistors
- USB differential pair routing
- ESD protection
- 5V power input

---

## CAN Interface

CAN transceiver connected to the STM32.

Features:

- CANH
- CANL
- Optional 120Ω termination
- External CAN connector

---

## Power System

USB 5V input

↓

ESD Protection

↓

Filtering

↓

3.3V Linear Regulator

↓

STM32 + CAN Transceiver

---

# PCB Design

## Layer Stack

Layer 1
- Components
- High-speed signals
- Power routing

Layer 2
- Solid Ground Plane

Layer 3
- Solid Ground Plane

Layer 4
- Signal Routing

---

# PCB Layout Considerations

## USB Differential Pair

- Routed as matched differential pair
- Short routing
- Minimal discontinuities
- Consistent spacing

---

## Power Distribution

- Wide power traces
- Local decoupling
- Filtered 3.3V rail
- Short regulator output path

---

## Crystal Placement

- Crystal placed immediately adjacent to MCU
- Short OSC_IN / OSC_OUT traces
- Symmetric routing

---

## Decoupling

100nF capacitors placed close to VDD pins.

Power traces kept short to minimize loop inductance.

---

## Grounding

- Dual internal solid ground planes
- Exposed thermal pad connected to ground
- Ground pours on outer layers
- Ground stitching vias

---

# Design Practices Used

- Differential pair routing
- Controlled impedance routing
- Ground return optimization
- Decoupling capacitor placement
- USB layout guidelines
- CAN layout guidelines
- DFM
- DFA
- Four-layer stackup
- ERC / DRC verification

---

# Software

Designed using:

- KiCad 9

---

# Manufacturing

Designed for standard PCB fabrication.

Typical fabrication capabilities:

- 4 Layers
- 0.15 mm trace/space
- 0.30 mm drill
- ENIG or HASL finish

---

# Repository Structure

```
CANBUS_Sniffer/
│
├── Hardware/
│   ├── Schematic/
│   ├── PCB/
│   ├── Gerbers/
│   ├── BOM/
│   ├── PickAndPlace/
│   └── Assembly_Drawings/
│
├── Firmware/
│
├── Images/
│   ├── pcb_layout.png
│   ├── pcb_3d.png
│   └── schematic.png
│
└── README.md
```

---

# Future Improvements

- Firmware implementation
- USB CDC interface
- CAN packet decoding
- CAN logging to PC
- Timestamping
- Bootloader support
- CAN FD support (future hardware revision)
- Additional status LEDs

---

# Lessons Learned

This project provided hands-on experience with:

- Professional PCB design workflow
- USB Type-C implementation
- CAN hardware design
- Differential pair routing
- Four-layer PCB stackup
- Signal integrity fundamentals
- Power integrity
- Component placement optimization
- KiCad workflow
- PCB design review and debugging

---

# License

This project is released under the MIT License.

---

# Author

**David Valle**

Electrical Engineer

Designed as part of a professional hardware engineering portfolio focused on embedded systems, PCB design, and robotics.
