# Stage 2: Nissan Leaf Bench Testing

This stage involves bench testing Nissan Leaf EV components to confirm their proper operation before integration into the Mini Cooper. Testing is structured into two key stages:

- **Stage 1:** Initial testing using the intact Leaf battery, OpenInverter Gen 2 Leaf board, Leaf accelerator pedal, and gear selector.
- **Stage 2:** Integration of Orion BMS and custom battery module repackaging.

---

## Objectives

- Verify the operation of Nissan Leaf drivetrain components (motor, inverter, charger, DC-DC converter).
- Install and configure the OpenInverter Gen 2 Leaf board for motor control and CAN integration.
- Test and integrate the original Leaf accelerator pedal and gear selector.
- Prepare for battery module repackaging and Orion BMS integration.

---

## Equipment Required

### EV Components:
- Nissan Leaf Gen 2 drivetrain:
  - Motor, inverter, gearbox assembly
  - Charger, DC-DC converter
  - Complete intact Leaf battery pack (Stage 1 testing)
  - Leaf accelerator pedal
  - Leaf gear selector unit
  - OpenInverter Gen 2 Leaf controller board
  - Orion BMS (Stage 2 integration)

### Supporting Equipment:
- High-voltage-rated cables and connectors
- Suitable fuses and HV contactors
- ESP32 microcontroller for CAN logging
- CAN interface hardware (e.g., MCP2515)
- Diagnostic tools (OBD-II scan tool, multimeter)
- Laptop for OpenInverter firmware flashing and configuration

### Safety Equipment:
- PPE (fire-resistant clothing, HV gloves, insulated footwear, safety glasses)
- Safety signage, barriers, and insulated tools rated for HV work

---

## Pre-Test Safety Steps

Adhere strictly to EV safety protocols:

- Conduct Job Safety Analysis (JSA).
- Review Nissan Leaf documentation and OpenInverter instructions.
- Restrict workspace with clearly marked HV safety signage.
- Assign responsible supervisor for safety oversight during testing.
- Verify availability of suitable fire-extinguishing equipment.

---

## Stage 1: Bench Test with Intact Leaf Battery, OpenInverter, Pedal, and Gear Selector

**Purpose:**  
Establish a known-working baseline and verify control systems, including the Leaf accelerator pedal and gear selector via OpenInverter integration.

**Procedure:**

### Step 1: Component Inspection and Setup
- Inspect components and arrange them safely on a stable, insulated bench.
- Confirm that all connectors, cables, and assemblies are in good condition.

### Step 2: OpenInverter Board Installation
- Safely disassemble Nissan Leaf inverter.
- Remove OEM inverter control board.
- Install OpenInverter Gen 2 Leaf board securely into inverter housing.
- Reassemble inverter securely.

### Step 3: Firmware Flashing & Configuration
- Connect laptop to OpenInverter board via USB or serial interface.
- Upload verified OpenInverter firmware suitable for Gen 2 Leaf.
- Configure motor/inverter parameters and ensure successful communication.

### Step 4: Accelerator Pedal and Gear Selector Integration
- Connect the Leaf accelerator pedal to the OpenInverter controller, verifying correct signal mapping.
- Connect Leaf gear selector unit to OpenInverter CAN interface.
- Validate pedal signal responsiveness and gear selection via OpenInverter software.

### Step 5: HV System Connection
- Connect battery pack to motor, inverter, charger, and DC-DC converter using OEM Nissan HV cables.
- Confirm secure and insulated connections.

### Step 6: CAN Bus and Diagnostics
- Connect ESP32-based CAN logger and diagnostic equipment.
- Configure software to monitor Leaf/OpenInverter CAN communications.

### Step 7: Power-up and Functional Tests
- Power up system carefully, monitoring error codes and warnings.
- Conduct initial functional tests:
  - Verify accelerator pedal input and motor responsiveness (controlled RPM tests).
  - Confirm gear selector inputs (Drive, Neutral, Reverse modes).
  - Check DC-DC converter output (stable 12V).
  - Test charger communication and basic functionality.

### Step 8: Data Logging and Documentation
- Capture detailed CAN data during tests.
- Document test outcomes, any faults or anomalies, and settings used.

---

## Stage 2: Integration of Orion BMS and Battery Module Repackaging

**Purpose:**  
Prepare for final installation by repackaging the battery modules into custom battery boxes and integrating the Orion BMS for enhanced control and monitoring.

**Procedure:**

1. **Battery Disassembly**
   - Safely disassemble the Nissan Leaf battery pack into separate modules following manufacturer's guidelines and HV safety protocols.

2. **Battery Box Design and Assembly**
   - Design battery boxes suitable for installation in the Mini Cooper.
   - Fabricate and assemble boxes ensuring proper insulation, mechanical protection, and thermal management.

3. **Orion BMS Integration**
   - Wire each battery module individually into the Orion BMS, ensuring correct cell balancing and monitoring connections.
   - Verify Orion BMS configuration settings against module specifications.

4. **Revised Bench Testing**
   - Connect battery modules in custom boxes to drivetrain components through Orion BMS.
   - Repeat power-up and functional checks, confirming accurate battery management and communication via Orion BMS.

5. **Validation and Documentation**
   - Document detailed performance data, confirming successful BMS operation.
   - Record all settings, wiring diagrams, and configurations for future integration steps.

---

## Safety and Cleanup After Testing

After completion of bench tests:

- Safely power down and isolate all HV components.
- Clearly label and securely store all tested and verified components.
- Document any issues for resolution prior to vehicle integration.

---

## Outcomes and Next Steps

Successful completion of these bench tests provides confidence in the components' condition and compatibility. Confirmed operation allows proceeding to the next stages of mechanical and electrical integration into the Mini Cooper chassis.

**Follow-up actions:**

- Analyze and archive all CAN and diagnostic data captured.
- Address any identified issues or anomalies from bench tests.
- Prepare components and documentation for Stage 3: Mini Cooper Disassembly.
