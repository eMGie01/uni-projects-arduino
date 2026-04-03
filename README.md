# Portfolio – Embedded, Control & Electronics Projects
**Author:** Marek Gałeczka

Welcome to my project portfolio.  
This repository is a curated index of my **embedded systems**, **control**, and **electronics** projects (mainly 2024–2025), including both **university thesis work** and advanced personal/lab projects.

Each linked project repository contains:
- full **source code**,
- a detailed **README** (features, architecture, hardware, my contribution),
- and in some cases **documentation PDFs** and **demo media**.

---

## Quick Links (Selected Projects)

1. **Programmable Active Load for 12 V Batteries (MSc Thesis)**  
   STM32 + power electronics + measurement + control + SD logging + PC GUI  
   Repo: https://github.com/eMGie01/2025-Active-Load/tree/0a08aab8c37f74552b0e7a624bf6ec7f1135b3a2

2. **STM32–ESP32 Modbus Gateway with Web Dashboard**  
   Modbus RTU + FreeRTOS + Wi‑Fi AP + HTTP/JSON + browser UI  
   Repo: https://github.com/eMGie01/2025-STM32-ESP32-Modbus-Gateway/tree/d837dffa72a54b2f02b5b202583b7a6b9d9b2faf

3. **Blood Smear Support Device (BSc Engineering Thesis)**  
   Stepper motion profile + homing + state machine, single‑button workflow  
   Repo: https://github.com/eMGie01/2024-Blood-Smear-Device/tree/2ca72fe21117e20a3a95ea1208c4e8cdf0e966be

4. **Motor PI Controller – DC Motor Speed Control with Encoder & TFT**  
   PI control loop timing + ISR encoder + anti‑windup + TFT visualization  
   Repo: https://github.com/eMGie01/2024-PI-Controller-for-Motor/tree/fd20f0c3c19d10897cf308aceab3bb2c8f75f47d

5. **Smart Rangefinder – Room Area & Distance Measurement (ESP32 + ToF + TFT)**  
   I²C sensor integration + UI state machine + units + averaging  
   Repo: https://github.com/eMGie01/2024-Smart-Sensor-Rangefinder/tree/0e3bd12754c62c66917afee0f4bc9c440a8d851b

---

## Highlights (Project Summaries)

### 1) Programmable Active Load for 12 V Batteries (Master’s Thesis)
A complete **hardware + firmware** system: a programmable active electronic load for testing 12 V batteries, supporting:
- **CC (Constant Current)**, **CR (Constant Resistance)**, **CP (Constant Power)**
- continuous operation up to approx. **14 A**

**Key elements**
- **Controller:** STM32 **NUCLEO‑L152RE** (STM32CubeIDE + HAL)
- **Power stage:** MOSFET + power resistors, thermal monitoring + fan
- **Precision measurement:** 2 × **MCP3561 24‑bit ADC** + **ADR441** reference
- **Control:** **PID + temperature compensation**
  - MOSFET behaviour modelled in LTspice → converted to LUTs → runtime interpolation
  - anti‑windup + clamping for safe operation
- **SD logging:** CSV logs via **FatFS** + RTC timestamps
- **PC integration:** UART + custom protocol + **C# desktop GUI**

**Skills demonstrated:** STM32 HAL (SPI/UART/TIM/RTC/GPIO), control systems (PID, anti‑windup), measurement and calibration, SD/FatFS, robust UART protocols, system‑level design.

Repo: https://github.com/eMGie01/2025-Active-Load/tree/0a08aab8c37f74552b0e7a624bf6ec7f1135b3a2

---

### 2) STM32–ESP32 Modbus Gateway with Web Dashboard
An end‑to‑end gateway showing a full path: **UART/Modbus → FreeRTOS tasks → HTTP/JSON API → browser UI**.

**Architecture**
- **STM32 NUCLEO‑L467RG:** Modbus RTU **slave** (register map + responses)
- **ESP32 DevKit:** Modbus RTU **master** + **Wi‑Fi AP** + **HTTP server**
- **Web app (HTML/CSS/JS):** served from ESP32 flash; live data + LED control

**Key features**
- Modbus RTU frames, CRC16, timeouts/retries
- FreeRTOS: tasks, queues, semaphores (UART events, parsing, polling, processing)
- JSON endpoints:
  - `/api/modbus` – live Modbus data
  - `/api/toggle` – ESP32 LED control
- Demo GIFs documented in project README

**Skills demonstrated:** ESP‑IDF, FreeRTOS, Modbus RTU, UART state machines, Wi‑Fi + HTTP servers, JSON APIs, embedded web UI.

Repo: https://github.com/eMGie01/2025-STM32-ESP32-Modbus-Gateway/tree/d837dffa72a54b2f02b5b202583b7a6b9d9b2faf

---

### 3) Blood Smear Support Device (BSc Engineering Thesis)
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

### 4) Motor PI Controller – DC Motor Speed Control with Encoder & TFT
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

### 5) Smart Rangefinder – Room Area & Distance Measurement
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

---

## Skills Demonstrated Across the Portfolio

**Embedded platforms**
- STM32 (CubeIDE + HAL): SPI, UART, TIM, RTC, GPIO, SD/FatFS
- ESP32: ESP‑IDF, FreeRTOS, Wi‑Fi AP, HTTP server

**Protocols & communication**
- Modbus RTU (frames, CRC16, timeouts, retries)
- UART protocols with framing/checksums
- HTTP/JSON endpoints for embedded web dashboards

**Control & runtime engineering**
- PI/PID control loops, anti‑windup, clamping
- timer-based execution, safe ISR → main-loop handoff
- temperature compensation using LUTs from simulation

**Electronics & measurement**
- high-resolution ADC measurement chain (24‑bit ADCs + precision reference)
- power electronics concepts (MOSFET linear region, thermal constraints)
- calibration, logging, diagnostic data capture

---

## Contact
If you’d like to discuss any of these projects:

- **Name:** Marek Gałeczka
- **Role goal:** Embedded / Firmware / IoT Developer
- **Email:** <marek.galeczka@outlook.com>
- **LinkedIn:** <https://www.linkedin.com/in/m-gałeczka/>

Feel free to open each project repository for full implementation details, architecture notes, and demos.