# Klipper Configuration: Anycubic Chiron + SKR 3 EZ + BLTouch

A production-ready, thoroughly documented `printer.cfg` for running Klipper on the Anycubic Chiron 3D printer, upgraded with the BigTreeTech SKR 3 EZ mainboard and BLTouch for automatic bed leveling. This configuration leverages TMC2209 stepper drivers in UART mode, dual Z synchronization, and custom macros for a streamlined, reliable 3D printing workflow. Designed for easy adoption and modification, this repository demonstrates advanced 3D printer firmware integration and professional documentation practices.

---

## Features

- **SKR 3 EZ Board Support:** Modern 32-bit mainboard with flexible connectivity and expandability.
- **BLTouch Auto Bed Leveling:** Accurate, repeatable mesh bed leveling for the Chiron's large-format bed.
- **Dual Z Motor Synchronization:** Improved gantry leveling and print quality using Klipper's `z_tilt`.
- **TMC2209 UART Mode:** Silent, efficient stepper drivers with current control and diagnostics.
- **Custom Macros:** Automated start/end print routines for consistent and reliable printing.
- **Professional Documentation:** Inline config comments and this README for easy setup and future maintenance.

---

## Table of Contents

- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Setup Instructions (KIAUH)](#setup-instructions-kiauh)
- [Configuration Highlights](#configuration-highlights)
- [Source Files](#source-files)
- [Troubleshooting](#troubleshooting)
- [Credits](#credits)

---

## Hardware Requirements

- **Printer:** Anycubic Chiron
- **Mainboard:** BigTreeTech SKR 3 EZ
- **Stepper Drivers:** TMC2209 (UART mode)
- **Bed Probe:** BLTouch (or compatible)
- **Host:** Raspberry Pi or similar SBC running Klipper (Mainsail/Fluidd/Octoprint)
- **Other:** Standard Chiron hardware, optional upgrades as desired

---

## Setup Instructions (KIAUH)

To install Klipper, Moonraker, and your web interface, please follow the official KIAUH instructions:

- [KIAUH GitHub Repository](https://github.com/dw-0/kiauh)

KIAUH (Klipper Installation And Update Helper) is a user-friendly tool for installing and managing Klipper, Moonraker, Mainsail, Fluidd, and related components. Visit the link above for the latest step-by-step guide and best practices for your hardware and operating system[2][6].

---

## Configuration Highlights

| Feature                | Section(s)                | Notes                                                            |
|------------------------|--------------------------|------------------------------------------------------------------|
| Dual Z Motors          | `[stepper_z]`, `[stepper_z1]`, `[z_tilt]` | Synchronized Z for stable gantry                                  |
| BLTouch                | `[bltouch]`, `[safe_z_home]`, `[bed_mesh]` | Automated mesh and safe homing                                    |
| TMC2209 Drivers        | `[tmc2209 ...]`          | UART mode for silent, monitored stepper operation                 |
| Custom Macros          | `[gcode_macro START_PRINT]`, `[gcode_macro END_PRINT]` | Consistent print start/end routines                               |
| Bed Leveling Screws    | `[bed_screws]`           | For manual tramming if needed                                     |
| Virtual SD Card        | `[virtual_sdcard]`       | Enables G-code upload and printing via web interface              |

---

## Source Files

- [`printer.cfg`](printer.cfg) — Complete, annotated Klipper configuration for Anycubic Chiron with SKR 3 EZ and BLTouch.

---

## Troubleshooting

- **Connection Issues:** Ensure the correct USB serial path is set in `[mcu]`.
- **Stepper Motor Issues:** Verify TMC2209 UART wiring and correct `uart_pin` assignments.
- **Firmware Issues:** Always use the latest SKR 3 EZ Klipper firmware as recommended by [BigTreeTech](https://github.com/bigtreetech/SKR-3/tree/master/Firmware/Klipper).

---

## Credits

- Configuration by [RoffleSauce]

