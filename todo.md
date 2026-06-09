# CamSat CFS-1 — TODO

This is a tracker for the Tasks that I have to complete for this Project

---

## 🧠 Phase 1 — System Design (Architecture First)

- [ ] Create System architecture and Diagrams (flight + ground + sim)
- [ ] Design subsystems
- [ ] Define message/telemetry protocol structure
- [ ] Create spacecraft mode state machine (BOOT / SAFE / NOMINAL / MISSION / RECOVERY)
- [ ] Create initial system diagrams (block + data flow)
- [ ] Define software interfaces (C headers / Python APIs)

---

## 🧱 Phase 2 — Core Flight Software Foundation

- [ ] Set up C flight software project structure
- [ ] Implement subsystem base framework (service template)
- [ ] Implement flight executive (mode manager)
- [ ] Implement command handler (telecommand parsing + routing)
- [ ] Implement telemetry generator
- [ ] Implement logging subsystem (event + system logs)
- [ ] Implement heartbeat/health monitoring system

---

## ⚙️ Phase 3 — Subsystem Simulation Layer

- [ ] EPS (Power system simulation: battery, load, charging)
- [ ] ADCS (Attitude simulation: orientation, angular velocity)
- [ ] Payload subsystem (generic payload simulator)
- [ ] Communications subsystem (telemetry + command transport)
- [ ] Subsystem failure injection system (for testing FDIR)

---

## 🚨 Phase 4 — Fault Detection, Isolation & Recovery (FDIR)

- [ ] Implement watchdog timer system
- [ ] Detect subsystem heartbeat failures
- [ ] Implement automatic subsystem restart logic
- [ ] Implement SAFE MODE transition logic
- [ ] Implement degraded mode operation handling
- [ ] Define fault prioritisation system (critical vs non-critical)

---

## 🛰️ Phase 5 — Ground Segment (Mission Control)

- [ ] Build ground station application (Python/Flask)
- [ ] Implement telemetry viewer dashboard
- [ ] Implement command console interface
- [ ] Implement mission event log viewer
- [ ] Implement subsystem health display
- [ ] Add real-time telemetry streaming support

---

## 📡 Phase 6 — Communication Layer

- [ ] Define packet structure (CCSDS-inspired format)
- [ ] Implement serialization/deserialization layer
- [ ] Implement transport layer (UDP / ZeroMQ)
- [ ] Implement command acknowledgement system
- [ ] Add telemetry timestamping and sequencing

---

## 🧪 Phase 7 — Testing & Validation

- [ ] Unit tests for flight software modules (C/C++)
- [ ] Integration tests for subsystem interactions
- [ ] Simulation-based mission scenario tests
- [ ] Fault injection test suite
- [ ] Continuous integration pipeline (GitHub Actions)

---

## 🧰 Phase 8 — Hardware-in-the-Loop (HIL)

- [ ] Integrate Raspberry Pi as onboard computer
- [ ] Connect an IMU sensor (e.g. MPU6050 / BNO055)
- [ ] Connect an temperature sensor
- [ ] Simulate sensor data injection pipeline
- [ ] Validate real-time telemetry flow from hardware

---

## 📊 Phase 9 — Simulation & Mission Scenarios

- [ ] Orbital dynamics simulator (basic physics model)
- [ ] Power consumption simulation over mission timeline
- [ ] Thermal variation simulation
- [ ] Mission scenario scripting system
- [ ] Replay system for telemetry logs

---

## 🚀 Phase 10 — Polish & Portfolio Readiness

- [ ] Full system documentation cleanup
- [ ] Architecture diagrams finalised
- [ ] Demo video of full system running
- [ ] Example mission scenario walkthrough
- [ ] Performance and reliability summary
- [ ] Final GitHub README polish
