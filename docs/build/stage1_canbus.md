# Stage 1: Log Mini CAN Bus

This stage documents capturing and decoding CAN bus data from the stock Mini to support later integration and spoofing.

---

## Objectives

- Tap into Mini CAN lines safely
- Capture baseline CAN traffic while driving
- Identify key signals (RPM, speed, fuel, coolant temp, indicators)

---

## Setup Used

- ESP32 with MCP2515 (CH340 USB preferred for 1M baud)
- SavvyCAN using GVRET serial at 1,000,000 baud
- Temporary inline CAN harness with proper termination

---

## Procedure

1. Connect MCP2515 to ESP32 (SPI) and flash ESPRET/GVRET firmware
2. Verify clean GVRET stream in serial monitor (no extra debug output)
3. Connect to vehicle CAN at OBD-II or accessible junction
4. Drive and record frames across varied conditions (idle, cruise, accel, braking)

---

## Findings

- Note discovered IDs and scaling here as they are confirmed
- Map signals with timestamps and context (gear, speed, etc.)

---

## Artifacts

- Raw log files: to be added
- Preliminary DBC or signal map: to be added

---

## Next Steps

- Validate repeatability of key signals
- Prepare minimal set needed for cluster operation after EV swap

