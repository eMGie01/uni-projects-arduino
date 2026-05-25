# University – Embedded, Control & Electronics Projects
**Author:** Marek Gałeczka

Welcome to my project dump.  
This repository is a curated index of my **embedded systems**, **control**, and **electronics** projects (mainly 2023–2024), including both **university thesis work**.

Each linked project repository contains:
- full **source code**,
- a detailed **README** (features, architecture, hardware, my contribution),
- and in some cases **documentation PDFs** and **demo media**.

---

## Quick Links (Selected Projects)

1. **Blood Smear Support Device (BSc Engineering Thesis)**  
   Stepper motion profile + homing + state machine, single‑button workflow  
   Repo: https://github.com/eMGie01/2024-Blood-Smear-Device/tree/2ca72fe21117e20a3a95ea1208c4e8cdf0e966be

2. **Motor PI Controller – DC Motor Speed Control with Encoder & TFT**  
   PI control loop timing + ISR encoder + anti‑windup + TFT visualization  
   Repo: https://github.com/eMGie01/2024-PI-Controller-for-Motor/tree/fd20f0c3c19d10897cf308aceab3bb2c8f75f47d

3. **Smart Rangefinder – Room Area & Distance Measurement (ESP32 + ToF + TFT)**  
   I²C sensor integration + UI state machine + units + averaging  
   Repo: https://github.com/eMGie01/2024-Smart-Sensor-Rangefinder/tree/0e3bd12754c62c66917afee0f4bc9c440a8d851b

---

## Highlights (Project Summaries)

### 1) Blood Smear Support Device (BSc Engineering Thesis)
A mechatronic device that automates the **blood smear** motion on microscope slides to improve repeatability and reduce manual workload.

**Key features**
- **MCU:** Arduino‑compatible (ATmega328 / UNO‑class)
- Stepper + **A4988**, limit switch, belt + linear guides (3D‑printer‑style mechanics)
- Firmware: simple **state machine** and firmware‑defined **motion profile**
- Operator workflow:
  - 1st press → homing/calibration
  - 2nd press → full smear cycle (forward + oscillation + return)
- Motor driver enabled only during motion (reduced heating/noise/power)

**Skills demonstrated:** state machines for mechanical processes, homing with limit switch, stepper control, motion profiling, translating a manual procedure into deterministic embedded behaviour.

Repo: https://github.com/eMGie01/2024-Blood-Smear-Device/tree/2ca72fe21117e20a3a95ea1208c4e8cdf0e966be

---

### 2) Motor PI Controller – DC Motor Speed Control with Encoder & TFT
A closed-loop **DC motor speed controller** implemented in an Arduino‑compatible environment.

**Key features**
- Quadrature encoder feedback (ISR)
- **PI regulator** (P + I) in fixed time base (`micros()`)
- **Anti‑windup** and output clamping
- H‑bridge motor driver + two buttons (direction + start/stop)
- **TFT ST7735** live dashboard showing speed and control error
- Serial output for analysis and tuning

**Skills demonstrated:** motor control, timing discipline, ISR data sharing, PI control, anti‑windup, embedded visualization/debug logging.

Repo: https://github.com/eMGie01/2024-PI-Controller-for-Motor/tree/fd20f0c3c19d10897cf308aceab3bb2c8f75f47d

---

### 3) Smart Rangefinder – Room Area & Distance Measurement
A smart rangefinder that measures distance and computes rectangular room area using two measurements.

**Key features**
- **ESP32** + **TF‑Luna ToF** sensor (I²C)
- **TFT ST7735** UI + 3 button inputs (trigger/menu/unit)
- Two modes: distance / area (two measurements → \( A = d_1 \cdot d_2 \))
- Units: cm/mm/inch and cm²/mm²/inch²
- Measurement averaging (11 samples) for stability
- Interrupt-driven button handling with debouncing in main loop

**Skills demonstrated:** sensor integration (I²C), embedded UI design, state machines, unit handling, practical input handling.

Repo: https://github.com/eMGie01/2024-Smart-Sensor-Rangefinder/tree/0e3bd12754c62c66917afee0f4bc9c440a8d851b
