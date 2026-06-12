# CamSat Flight Stack (CFS-1)

A solo project exploring Embedded Flight Software

**Lead Engineer** Cam McKay

![Alt Text](https://www.esa.int/var/esa/storage/images/esa_multimedia/images/2021/04/getting_cubesats_moving/23243105-1-eng-GB/Getting_CubeSats_moving.gif)

---

## Overview

CamSat is an CubeSat flight software architecture designed to simulate onboard spacecraft operations.

It is intended as an engineering demonstrator for embedded systems, spacecraft software design, and real-time systems development.

---

## System Architecture

The system is split into two main segments:

### Flight Segment (Onboard Computer)

Runs on Embedded Linux and simulates spacecraft subsystems:

* Power System (EPS)
* Attitude Determination and Control System (ADCS)
* Payload Management
* Communications Subsystem
* Fault Detection, Isolation & Recovery (FDIR)
* Flight Executive (Mode Manager)

Subsystems operate as independent services communicating via a structured message interface.
---
## Core Features

### Flight Software

* Modular subsystem architecture
* State machine-based mission mode control
* Real-time telemetry generation
* Command handling and routing
* Watchdog and health monitoring services

### Fault Management (FDIR)

* Automatic anomaly detection
* Subsystem restart and recovery logic
* Safe mode entry on critical failure
* Degraded mode operations

### Telemetry & Telecommand

* Structured packet-based communication protocol
* Command validation and execution pipeline
* Time-stamped telemetry logging

### Simulation
* Hardware-in-the-loop capable design
* Sensor and subsystem simulation layer
* Mission scenario replay
---

## Technologies

* C / C++ (Flight software)
* Python (Ground segment, simulation tools)
* Linux (Embedded flight computer environment)
* Git (Version control)
* CI/CD (Automated testing pipelines)

---

## Design Philosophy

This project follows principles inspired by real spacecraft flight software:

* Deterministic behaviour under constrained conditions
* Fault tolerance as a core requirement, not an afterthought
* Strict separation of subsystems
* Mode-based spacecraft control architecture
* Test-driven development with simulation-first validation

---

## Mission Modes

The spacecraft operates in the following modes:

* **BOOT** – System initialization
* **SAFE MODE** – Minimal functionality, survival state
* **NOMINAL** – Standard operations
* **MISSION MODE** – Payload active
* **RECOVERY** – Post-fault recovery operations

---

## Example Use Case

1. Spacecraft boots into SAFE MODE
2. Health checks pass → transitions to NOMINAL
3. Ground station sends `START_PAYLOAD` command
4. Payload subsystem activates
5. Telemetry stream begins
6. Fault detected → ADCS restart triggered automatically
7. System returns to NOMINAL state

---

## Goals of the Project

* Demonstrate real-world spacecraft software architecture
* Implement embedded-style system design on Linux
* Showcase fault-tolerant distributed subsystem design
* Simulate mission operations and telemetry workflows
* Expand knowledge of Embedded Systems and Flight Software
* Explore Space Engineering Design Princibles

---

## Author

Cam McKay
Software Engineer — Safety-Critical Systems / Embedded Software

Interest areas: spacecraft systems, embedded Linux, orbital dynamics, autonomous systems
