# Stage 1: Log and Identify Mini CAN Bus

This stage involves capturing and interpreting the CAN (Controller Area Network) bus signals from the Mini Cooper. Successfully identifying these signals is crucial for integrating the Nissan Leaf electric drivetrain and maintaining vehicle functionality.

---

## Objective

To identify critical CAN bus signals from the Mini Cooper's systems, including:

- Vehicle speed
- RPM
- Dashboard indicators (e.g., temperature, fuel level)
- ABS and Stability Control signals
- Steering angle and torque requests

---

## Known CAN Bus Information (To Be Verified)

Based on publicly available sources, the following CAN IDs and signal mappings have been identified for the Mini Cooper R53. These mappings require confirmation through direct testing:

| Signal               | CAN ID | Offset (bytes) | Length (bytes) | Conversion Formula                   | Source |
|----------------------|--------|----------------|----------------|--------------------------------------|--------|
| Throttle Position    | 0x809  | 6              | 1              | (B6 / 254) * 100                     | [Autosport Labs](https://wiki.autosportlabs.com/CAN_Bus_database) |
| Engine Temperature   | 0x809  | 2              | 1              | (B2 * 0.75) - 48.373                 | [Autosport Labs](https://wiki.autosportlabs.com/CAN_Bus_database) |
| RPM                  | 0x790  | 3-4            | 2              | ((B4 * 256) + B3) / 6.4              | [Autosport Labs](https://wiki.autosportlabs.com/CAN_Bus_database) |

*Note: These values are based on community-shared data and should be validated through direct CAN bus logging.*

---

## Equipment Required

- ESP32 microcontroller with CAN bus module (e.g., MCP2515)
- OBD-II CAN bus connector and breakout cable
- Laptop or PC for data logging
- Diagnostic software (e.g., SavvyCAN, CANalyzer)
- Manufacturer wiring diagrams and service manuals for Mini Cooper R53

**Safety Equipment:**

- Standard PPE (gloves, safety glasses)
- Insulated tools for electrical connections

---

## Pre-Work Safety Steps

Before commencing, ensure all personal and vehicle safety precautions are met:

- Perform a Job Safety Analysis (JSA)
- Review Mini Cooper manufacturer documentation
- Remove jewellery, watches, and any conductive materials
- Clearly mark and restrict the CAN logging workspace
- Assign a responsible person to oversee safety during the logging session

---

## Procedure: CAN Bus Logging

**Identify CAN Bus Access Point**

   - Locate the OBD-II port under the dash, typically accessible in the driver’s footwell.
   - Verify CAN bus wiring from the Mini’s electrical schematics.

**Set Up the Logging Hardware**

  - Connect the ESP32 and CAN interface (MCP2515) to the Mini Cooper via OBD-II breakout cable.
  - Ensure connections are secure and properly insulated.

**Configure Software**

   - Launch CAN logging software (e.g., SavvyCAN).
   - Set the correct baud rate (commonly 500 kbps for Mini R53).

**Begin Logging**

   - Start the vehicle and systematically activate all controls (lights, indicators, brake, accelerator, steering, etc.).
   - Record CAN traffic with timestamps for easier signal identification.

**Signal Identification**

   - Analyze logged data to correlate recorded CAN IDs with specific vehicle functions.
   - Create a table documenting identified signals, CAN IDs, and expected data formats.

---

## Chrono Pack Signal Mapping

The Mini Cooper's Chrono Pack includes additional gauges such as oil temperature and pressure. These signals may not be present on the standard CAN bus and might require direct sensor connections or alternative methods for integration. Further investigation and testing are necessary to determine the exact signal pathways and integration techniques.

---

## Data Documentation Template

| Signal               | CAN ID | Offset (bytes) | Length (bytes) | Conversion Formula                   | Notes                 |
|----------------------|--------|----------------|----------------|--------------------------------------|-----------------------|
| Vehicle Speed        | TBD    | TBD            | TBD            | TBD                                  | To be determined      |
| Engine RPM           | TBD    | TBD            | TBD            | TBD                                  | To be determined      |
| Coolant Temperature  | TBD    | TBD            | TBD            | TBD                                  | To be determined      |
| ABS/ESC Activation   | TBD    | TBD            | TBD            | TBD                                  | To be determined      |

*Note: Replace 'TBD' with actual values upon confirmation through testing.*

---

## Post-Logging Safety Steps

- Ensure the vehicle is switched off and secured.
- Remove and safely store logging equipment.
- Document findings clearly and store securely for future stages.

---

## Outcomes and Next Steps

Successful CAN bus logging and identification will enable the next stages, including bench-testing of Leaf components and integration planning. Accurate CAN data ensures compatibility and safe operation after conversion.

---

*Follow-up actions:*

- Prepare detailed documentation of findings.
- Verify uncertain signals through repeated logging if necessary.
- Ensure findings are clearly accessible for Stage 7 (CAN Bus Spoofing).

