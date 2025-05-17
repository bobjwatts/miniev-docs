# Stage 7: CAN Bus Integration & Spoofing

This stage focuses on integrating the EV system into the Mini Cooper’s existing CAN bus architecture. The objective is to ensure the vehicle’s original systems—including dash cluster, indicators, and subsystems—function correctly by spoofing or bridging CAN messages from the new EV components.

---

## Objectives

- Interface Mini Cooper CAN bus with EV drivetrain and Orion BMS.
- Translate or spoof CAN signals to retain factory dash functionality.
- Ensure safe and predictable communication between all subsystems.
- Lay the groundwork for long-term diagnostics and performance monitoring.

---

## Equipment Required

### Components:
- ESP32 microcontroller with CAN transceiver (e.g., MCP2515 or SN65HVD230)
- OpenInverter Leaf board (from Stage 2)
- Orion BMS (from Stage 5)
- CAN bus breakout wiring or gateway harness
- 12V to 5V converters for ESP32
- Diagnostic laptop or mobile device

### Tools & Software:
- SavvyCAN or similar CAN analysis tool
- Wireshark with CAN interface (optional)
- Arduino IDE or PlatformIO for ESP32 programming
- CAN databases (DBC files if available), wiring diagrams

### Safety Equipment:
- PPE: gloves, eye protection
- Safe power setup (precharged system only)
- Clearly marked test area

---

## Pre-Integration Safety Steps

- Isolate HV battery during CAN work unless low-voltage testing only.
- Confirm all CAN wiring is 12V-safe and fused as needed.
- Document OEM Mini Cooper wiring and signal expectations.
- Perform a Job Safety Analysis (JSA) specific to embedded electronics and comms.

---

## Procedure: CAN Integration

### Step 1: Logging and Decoding Mini CAN Signals
- Connect CAN reader to Mini’s OBD-II port.
- Log messages under varying vehicle states:
  - Ignition on/off
  - Vehicle in motion (via test drive or wheel speed emulation)
  - HVAC, indicator, and cluster events
- Identify signals for:
  - RPM, speed, fuel level, coolant temp, warning lights, etc.
  - Chrono Pack-specific signals (if applicable)

### Step 2: Logging OpenInverter and Orion BMS CAN Output
- Capture CAN output from Leaf motor controller and Orion BMS.
- Note message IDs, byte positions, and update rates for key data:
  - Motor RPM, inverter temp, throttle position, battery SOC, voltages, temps.

### Step 3: ESP32 CAN Spoofing Development
- Develop firmware to read EV CAN messages and repackage them into Mini-compatible signals.
- Maintain correct message timing and structure to avoid triggering fault lights or system resets.
- Use simple checksum and scaling if required (reverse engineered from original logging).

Example:
```cpp
// Pseudo-code
if (leafCanMsg.id == 0x1D4) { // Motor RPM
  miniMsg.id = 0x790;
  miniMsg.data[2] = scaled_rpm_low;
  miniMsg.data[3] = scaled_rpm_high;
  sendCan(miniMsg);
}
