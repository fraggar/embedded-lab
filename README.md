Learning embedded firmware from the ground up, hand-written, on the way to an
open-source energy gateway and my master's thesis.

**Goal:** firmware that reads an energy device (inverter, meter, battery) and
publishes it to Home Assistant, written and understood by me.

**Stack:** Zephyr RTOS. Course: Nordic DevAcademy *nRF Connect SDK Fundamentals*.

**AI rule:** AI is a tutor here, never the author — see [CLAUDE.md](CLAUDE.md).

## Roadmap
Each step ends with something working and a short entry in [LOG.md](LOG.md).

- [ ] **0. Setup** — Zephyr toolchain, `west`, first build and flash, debugger attached
- [ ] **1. Basics** — blinky, GPIO interrupt, UART echo, logging
- [ ] **2. Modbus by hand** — RS-485 + UART, my own RTU frame and CRC16, read one register
      from a PC simulator; then switch to Zephyr's Modbus subsystem and compare
- [ ] **3. Concurrency** — poll thread, message queue, publish thread, timers
- [ ] **4. Network** — Wi-Fi/Ethernet, MQTT, Home Assistant MQTT discovery
- [ ] **5. Robustness** — watchdog, settings storage, reconnects, OTA
- [ ] **6. Generalise** — SunSpec model discovery and parsing (thesis core)

## Hardware
- Dev board: TBD (ESP32 or nRF; decided in step 0)
- RS-485 transceiver module for the board, USB-RS485 adapter for the PC
- Modbus slave simulator on the PC (no real device needed for steps 2–3)
- Later: logic analyzer (cheap 8-channel is enough)
- At home: Shelly 3EM and Tibber Pulse (no Modbus inverter identified yet)

## Layout
- `exercises/` — small standalone apps, one per topic
- `gateway/` — the real firmware, from step 3 on
- `thesis/` — notes and drafts (no AI-written text)
