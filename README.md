# CANBUS Sniffer

A compact USB-to-CAN interface built around an STM32 microcontroller and CAN transceiver for learning high-speed PCB design, USB routing, power supply design, and embedded hardware development.

**Version:** V1.0.0

---

# Overview

The purpose of this project is to design a complete CAN Bus Sniffer PCB from schematic capture through PCB layout using professional design practices.

The board receives power over USB Type-C, regulates the voltage to 3.3V, communicates over a CAN bus transceiver, and provides programming/debugging through an SWD interface.

Rather than simply creating a functional board, the primary goal was to practice professional PCB design methodologies including:

- Component placement
- Differential pair routing
- Power distribution
- Ground plane implementation
- Decoupling capacitor placement
- Controlled impedance routing
- Design for Manufacturability (DFM)
- Design for Assembly (DFA)
- Design Rule Checking (DRC)

---

# Features

- USB Type-C power input
- STM32 microcontroller
- CAN Bus transceiver
- USB Full-Speed differential pair routing
- 3.3V LDO regulator
- Reverse polarity protection
- TVS protection
- Power indication LEDs
- CAN activity LEDs
- SWD programming header
- RESET pushbutton
- BOOT pushbutton
- Four mounting holes
- Four-layer PCB

---

# Hardware Specifications

| Item | Specification |
|------|---------------|
| MCU | STM32F0 Series |
| CAN Transceiver | SN65HVD230 Compatible |
| USB | USB Type-C (USB 2.0 Full Speed) |
| Input Voltage | 5V USB |
| Logic Voltage | 3.3V |
| PCB Layers | 4 |
| PCB Thickness | 1.6 mm |
| Differential Pair | USB D+ / D− |
| Mounting | 4 Mounting Holes |

---

# PCB Stackup

Layer 1
- Components
- Signal Routing
- USB Differential Pair

Layer 2
- Solid Ground Plane

Layer 3
- Solid Ground Plane

Layer 4
- Signal Routing
- Power Distribution

Using two continuous internal ground planes provides:

- Low impedance return paths
- Improved signal integrity
- Reduced EMI
- Better high-frequency performance
- Easier routing of USB differential pairs

---

# Design Decisions

## USB Type-C

A USB Type-C connector was selected for modern compatibility.

USB CC resistors were included to properly advertise the board as a USB device.

The USB D+ and D− signals were routed as a controlled impedance differential pair using KiCad's differential pair router.

Design considerations included:

- Matched trace lengths
- Constant spacing
- Minimal discontinuities
- Short routing from connector to ESD protection
- Minimal via usage

---

## Differential Pair Routing

USB Full-Speed operates at 12 Mbps.

Although USB Full-Speed is less demanding than USB High-Speed, good routing practices were still followed:

- Controlled impedance differential pair
- Matched lengths
- Constant spacing
- Smooth 45° bends
- Short routing distance
- Minimal skew

---

## Power Supply

The board receives 5V from USB.

Power then passes through:

USB Type-C

↓

Protection

↓

Filtering

↓

3.3V LDO

↓

STM32 + CAN Transceiver

Separate filtering and decoupling were added for improved power integrity.

---

## Decoupling Strategy

Each power pin is locally decoupled using ceramic capacitors placed as close as possible to the IC supply pins.

Goals:

- Reduce switching noise
- Supply transient current
- Improve power stability
- Reduce EMI

---

## CAN Interface

The CAN transceiver converts the STM32 CAN peripheral into differential CANH/CANL signals.

Features include:

- Differential signaling
- CAN termination option
- Noise immunity
- Automotive compatible interface

---

## Grounding Strategy

The design uses:

- Internal Ground Plane (Layer 2)
- Internal Ground Plane (Layer 3)
- Top Ground Pour
- Bottom Ground Pour
- Via stitching

Benefits include:

- Continuous return paths
- Lower ground impedance
- Improved EMC
- Better thermal performance

The STM32 exposed ground pad is connected directly into the internal ground planes through a dedicated thermal via.

---

# PCB Design Considerations

During layout the following practices were used:

- Functional component grouping
- Short crystal routing
- Short decoupling paths
- Wide power traces
- Differential pair routing
- Ground stitching
- Clean routing with minimal unnecessary vias
- Consistent trace widths
- Design Rule Check (DRC) verification

---

# Software Used

- KiCad 9
- STM32CubeMX
- STM32CubeIDE

---

# Images

## Schematic

<p align="center">
  <img src="Images/schematic.png" width="1000">
</p>

---

## PCB Layout

### Routed PCB

<p align="center">
  <img src="Images/pcb_layout.png" width="1000">
</p>

### Routed PCB with Ground Pours

<p align="center">
  <img src="Images/pcb_layout_w_gndpours.png" width="1000">
</p>

---

## 3D PCB

### 3D Render

<p align="center">
  <img src="Images/pcb_3d.png" width="800">
</p>

### 3D Render with Ground Pours

<p align="center">
  <img src="Images/pcb_3d_w_gndpours.png" width="800">
</p>

---

# Project Status

Current Status:

- ✔ Schematic Complete
- ✔ PCB Layout Complete
- ✔ Design Rule Check Passed
- ✔ 3D Model Generated
- ✔ GitHub Documentation Complete

Future Improvements:

- Firmware development
- CAN frame decoding
- USB CDC communication
- PC desktop application
- Enclosure design
- Hardware validation and bring-up
- Oscilloscope verification of USB and CAN signals

---

# Lessons Learned

This project provided practical experience with:

- USB Type-C implementation
- USB differential pair routing
- Controlled impedance routing
- Four-layer PCB stackup
- Ground plane design
- Decoupling capacitor placement
- Power distribution
- CAN bus hardware
- STM32 hardware design
- PCB Design Rule Checks
- KiCad PCB workflow
- DFM and DFA considerations
- Professional PCB documentation

---

# License

This project is released under the MIT License.
