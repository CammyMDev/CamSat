# CamSat Flight Stack — CS-FS1

**Lead Engineer:** Cam McKay  
**Hardware:** STM32F446RE · FreeRTOS  
**Status:** 🟡 In Development

![Alt Text]https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2021/04/getting_cubesats_moving/23243105-1-eng-GB/Getting_CubeSats_moving.gif)

---

## What is this?

CamSat is my personal CubeSat flight software stack a solo engineering 
project building real spacecraft flight software from the ground up.

It runs on an STM32F446RE microcontroller with FreeRTOS and is designed 
around the same architecture principles used in professional spacecraft 
software modular subsystems, a hardware abstraction layer that lets the 
same code run on real hardware or a Linux simulation, CCSDS-inspired 
telemetry, and fault protection built in from day one rather than bolted 
on at the end.

---

## Hardware

| Component | Details |
|---|---|
| Flight computer | STM32F446RE (Nucleo-F446RE dev board) |
| RTOS | FreeRTOS via CMSIS-V2 |
| IMU | MPU-6050 (I2C) — ordered |
| Magnetometer | HMC5983 (I2C) — ordered |
| Radio | SX1276 LoRa 433MHz (SPI) — ordered |
| Flash storage | W25Q128 16MB (SPI) — ordered |

---

## Architecture

The key design decision is the Hardware Abstraction Layer (HAL). 
Every hardware access goes through `hal.h` — a fixed interface that 
never changes. Behind it sits either `hal_stm32.c` (real hardware) 
or `hal_sim.c` (Linux simulation fed by a Python physics engine). 
The flight logic above the HAL doesn't know or care which one it's 
talking to.

---

## Subsystems

**ADCS — Attitude Determination & Control**  
Reads IMU and magnetometer, runs an Extended Kalman Filter for 
attitude estimation, commands magnetorquers. 100Hz task.

**EPS — Electrical Power System**  
Monitors battery voltage, current draw, and solar panel power. 
Triggers low-power mode when battery drops below threshold.

**Comms**  
AX.25 packet framing over SX1276 LoRa radio. Handles telemetry 
downlink and command uplink. CCSDS-inspired packet format with 
CRC16 integrity checking.

**Fault Protection**  
Three-level response inspired by JPL fault management philosophy. 
Subsystem-level retry → fault protection task disable → hardware 
watchdog reset. The watchdog task is CRITICAL priority — if it 
stops running, the MCU resets.

**Flight State Machine**  
Eight mission states: BOOT → DETUMBLE → SAFE → NOMINAL → 
PAYLOAD_OPS → DOWNLINK → LOW_POWER → FAULT. Each state has 
defined entry actions, periodic behaviour, and sensor-driven 
transition guards.

---

## Telemetry Format

50-byte packet, CCSDS Space Packet Protocol inspired. Transmitted 
every 5 seconds during nominal operations.

---

## Why am I building this?

I'm a software engineer working in safety-critical defence systems, 
who has a love for space and space technology. This project is building the thing I want to work on professionally, 
learning the standards and architecture patterns that real spacecraft 
teams use, and having something to show for it.

If you're doing something similar or working in the space industry 
and want to chat, feel free to reach out.

---

**Cam McKay** — Software Engineer  

*Started April 2026*
