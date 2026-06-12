# CamSat CFS-1 — TODO

This is a tracker for the Tasks that I have to complete for this Project

---

## Step 1 - Design & Architecture
- [ ] Finalise the Architecture of the Project
- [ ] Define how the system and Subsystems will interface
- [ ] Design and Define telemetry and communication Packet Formats(CCSDS Inspired)
- [ ] State Machine Design
- [ ] Flow Diagram

## Step 2 - Foundation of the Software
- [ ] CMake Build System allow to Build for Simulation running and the STM
- [ ] Create the HAL To allow for Real Sensor and Generated Sensor Input
- [ ] FreeRTOS Groundwork
- [ ] Create the Statemachine
- [ ] Command Handler - Handle incoming packets
- [ ] Generate Telemetry - Health, Temp, Altitute ETC in the CCSDS packet
- [ ] Event Log - Log Events.
- [ ] Create a Watchdog to monitor Hardware

## Step 3 - Create Subsystems
- [ ] ADCS - Read an IMU Sensor and conduct EKF Attitude Estimation and Magnetorquer Control
- [ ] EPS - Monitor Battery Level and Trigger Low Power Mode if Needed
- [ ] Communications - AX.25, Encoding and Decoding Packets.
- [ ] Payload - (Need to Define what Exactly I want my Satellite to Do)
- [ ] Logger - Log flight events (Maybe to a W25Q128 using SPI)

## Step 4 - Fault Detection & Response
- [ ] Monitor Health - Each subsystem will report their current Health
- [ ] Level 1 Fault - Retire The Subsystem, Log the Event
- [ ] Level 2 Fault - Fault Protection, Disable Systems and Enter a Degraded Mode
- [ ] Level 3 Fault - Full Reset and Boot to SAFE.
- [ ] Safe Mode - Minimal Power Draw only Focus on Comms
- [ ] Injected Faults testing to make sure that The System Works


