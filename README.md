# STM32F103 4-Channel Motor Driver PCB

A compact STM32F103-based motor driver board supporting 4 independent DC motor
channels via dual TB6612FNG ICs, with onboard 3.3V regulation and full GND fill.

![3D Render](https://github.com/user-attachments/assets/e3a3fa0f-c090-41e8-be31-5f7679ed8c37)

## Features

- **MCU:** STM32F103CBTx (ARM Cortex-M3)
- **Motor Driver:** 2× TB6612FNG (4 channels total, PWM speed + direction control)
- **Power:** AMS1117-3.3V onboard voltage regulator
- **Switch:** Power ON/OFF slide switch with LED indicator
- **Programming:** 6-pin header (GND, 3.3V, BOOT, NRST, TX, RX)
- **Power Input:** Battery connector
- **Layers:** 2-layer PCB
- **Ground Plane:** Full GND copper fill
- **Unrouted Nets:** 0
- **DRC:** Clean

## PCB Screenshots

| PCB Layout | 3D Front | 3D Back |
|---|---|---|
| ![](https://github.com/user-attachments/assets/821b72bf-9e28-4020-9581-e057a2d6a5e9) | ![](https://github.com/user-attachments/assets/b264b154-e448-4e6d-b6a9-1fdec09420dd) | ![](https://github.com/user-attachments/assets/2e7e5ed8-7e9e-4fd3-b7f6-abbda7dcb328) |

## Schematic Overview

- STM32F103CBTx with power decoupling (22µF + 47µF + 0.1µF caps)
- 2× TB6612FNG: Motor A+B (driver 1), Motor C+D (driver 2)
- PWM signals routed from STM32 timers to driver PWMA/PWMB pins
- AMS1117-3.3V with bulk and bypass capacitors
- Power switch in series with battery input
  ![Schematic](https://github.com/user-attachments/assets/b4faf5d5-780b-4e20-a11c-2aec08b3d093)

## Design Decisions

| Decision | Reason |
|---|---|
| TB6612FNG over L298N | Higher efficiency, lower heat, smaller footprint |
| Dual TB6612FNG | 4 independent channels from single STM32 |
| GND copper fill | Motor switching noise suppression |
| Labeled motor connectors (A/B/C/D) | Clear assembly and debugging |

## Files

| File/Folder | Description |
|---|---|
| `https://github.com/user-attachments/files/27866326/stm.based.motor.driver.zip` | Production-ready Gerber files |
| `schematic.pdf` | Full KiCad schematic |
| `bom.csv` | Bill of materials |

## Tools

- KiCad 10.0
- STM32CubeIDE for firmware
- TB6612FNG + STM32F103 datasheets

## Author

**Simhadri Dharahaas** — ECE Undergraduate | PCB Design & Embedded Systems
[LinkedIn](https://www.linkedin.com/in/dharahaas-simhadri-b17b4b358?utm_source=share_via&utm_content=profile&utm_medium=member_android)
