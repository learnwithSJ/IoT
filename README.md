# Smart AI Plug

![Top-img](https://github.com/learnwithSJ/IoT/commit/6fd05ff5679e669197db008a941bd7b1b8bf792a)

![Side-img](https://github.com/learnwithSJ/IoT/commit/0b55e98b5b289068c1e1b8e2f64c918e45247a13)

![Bot-img](https://github.com/learnwithSJ/IoT/commit/025d5e4ec5016593152c4db0e94356bfdb574bb5)

An ESP32-S3 based IoT smart plug designed for remote and scheduled control of electrical appliances.

> **Project Status:** PCB Design Completed — Hardware Assembly and Testing Not Yet Performed.

## Overview

Smart AI Plug is a smart plug concept designed around the ESP32-S3 microcontroller. The system is intended to provide wireless appliance control along with scheduled operation.

The complete circuit and PCB were designed using **KiCad**.

## Features

* ESP32-S3 based design
* Single-channel relay control (SPDT)
* Wi-Fi and Bluetooth connectivity
* Relay-based appliance switching
* RTC-based scheduled operation
* USB-C interface
* Onboard RTC with battery backup (DS3231M + CH291-1220LF)
* Status LEDs - Network, Error, General indication
* Buzzer feedback (MLT-8530)
* 4x tactile switches for local control
* AC-DC power supply section
* PCB protection circuitry
* Compact PCB design

## 🏗️ System Architecture

```
220V AC Input
     │
     ▼
[F1 Fuse 500mA] ──→ [MOV RV1 Surge Protection]
     │
     ▼
[HLK-5M05] ──→ 5V DC
     │
     ├──→ [Relay K1 SPDT] ──→ Load Output (Screw Terminal J2)
     │
     └──→ [AMS1117-3.3] ──→ 3.3V DC
               │
               ├──→ [ESP32-S3-WROOM-1] ←→ WiFi / BLE
               ├──→ [DS3231M RTC] (I2C)
               ├──→ [Status LEDs]
               ├──→ [Buzzer MLT-8530]
               ├──→ [Tactile Switches x4]
               └──→ [USB-C] ──→ Firmware Flash / Serial Debug
```

---

## 🔧 Hardware Specifications

| Parameter | Details |
|---|---|
| Microcontroller | ESP32-S3-WROOM-1 |
| Input Voltage | 220V AC |
| Operating Voltage | 5V DC / 3.3V DC |
| Power Supply Module | HLK-5M05 (220VAC → 5VDC) |
| LDO Regulator | AMS1117-3.3 |
| Relay | SPDT — 1 Channel |
| RTC | DS3231M (I2C) |
| RTC Battery | CH291-1220LF (Coin Cell) |
| USB Connector | USB-C (USB 2.0) |
| ESD Protection | USBLC6-2P6 |
| Surge Protection | MOV 10D561K |
| Fuse | 500mA / 250V |
| Status LEDs | Red, Blue, Green |
| Buzzer | MLT-8530 |
| Switches | 4x Tactile + 1x Boot + 1x Reset |
| PCB Tool | KiCad 9.0.1 |
| Board Revision | Rev-v0.1.0A |

---

## PCB Design

The schematic and PCB layout were designed using **KiCad**.

## Repository Structure

```text
KiCad/          → KiCad schematic, PCB and project files
Documentation/  → Design documents and diagrams
Images/         → Project images
BOM/            → Bill of Materials
Firmware/       → Firmware documentation
```

## Project Status

The schematic and PCB layout have been completed in KiCad.

The current version is a **design/prototype-stage project**. Physical PCB fabrication, assembly, firmware deployment, and hardware testing have not yet been completed.

## Future Improvements

* Fabricate and assemble the PCB
* Develop and test ESP32-S3 firmware
* Add cloud-based appliance control
* Integrate voice assistant support
* Perform electrical safety and functional testing
* Optimize PCB size and power consumption

## 🏭 Manufacturing

Fabrication files are located in `Hardware/3-Manufacturing-Files/` and include:

- **Gerber files** - for PCB fabrication
- **BOM (Bill of Materials)** - component list with values and part numbers
- **CPL (Component Placement List)** - for SMT assembly

## Author

**Shubhank**
