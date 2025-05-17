# Stage 6: Electrical System Integration

This stage involves integrating all electrical subsystems within the converted Mini Cooper EV, including high-voltage (HV) and low-voltage (12V) circuits, the charger, DC-DC converter, safety interlocks, and essential power distribution systems.

---

## Objectives

- Safely integrate all HV and 12V electrical systems within the vehicle.
- Connect and validate the operation of the DC-DC converter and onboard charger.
- Establish power distribution, safety interlocks, and fuse protection.
- Lay the foundation for CAN bus integration and system-level coordination.

---

## Equipment Required

### Electrical Components:
- Nissan Leaf DC-DC converter
- Nissan Leaf onboard charger (or aftermarket)
- Orion BMS (from Stage 5)
- HV contactors, fuses, and pre-charge circuit
- 12V battery and fuse panel
- Safety interlock wiring
- HV wiring (orange, double-insulated, appropriately rated)

### Tools:
- Crimping and stripping tools
- Multimeter, pole tester, OBD-II reader
- Heat shrink, cable glands, protective conduit
- Insulated torque wrench and HV-safe hand tools

### Safety Equipment:
- HV PPE (gloves, safety boots, fire-resistant overalls)
- Eye protection and insulated mats
- Warning signage and lockout-tagout boards
- HV-rated test equipment

---

## Pre-Integration Safety Steps

- Conduct a Job Safety Analysis (JSA) for electrical work.
- Verify that HV battery pack is fully isolated and safe for work.
- Restrict access to electrical workspace and install HV warning signage.
- Confirm all tools are HV-safe and tested/tagged.

---

## Procedure: Electrical Integration

### Step 1: Low Voltage (12V) Power System
- Install and connect the 12V accessory battery in a secure location.
- Route power to the vehicle’s existing systems and new fuse panel.
- Connect 12V supply to Orion BMS, DC-DC converter, and other logic-level devices.
- Confirm voltage and grounding integrity.

### Step 2: DC-DC Converter Integration
- Connect the input side of the DC-DC converter to HV bus via fused and contactor-controlled lines.
- Output of the converter charges the 12V battery and supports low-voltage loads.
- Confirm correct voltage output under no-load and light-load conditions.

### Step 3: Onboard Charger Wiring
- Connect the onboard charger to the HV bus with proper fusing and contactor control.
- Wire AC input through a Type 2 (or J1772) EVSE inlet mounted externally on the Mini.
- Install charge interlock for HV safety during AC charging.

### Step 4: HV Wiring and Power Distribution
- Route HV cables through vehicle with appropriate shielding, grommets, and strain reliefs.
- Install fuses, main contactor, and pre-charge resistor circuit between HV battery and inverter.
- Integrate interlock wiring to disable HV output during maintenance or fault conditions.

### Step 5: Safety Systems and Interlocks
- Implement safety loop wiring through service disconnects, lid sensors, and crash interlock.
- Connect to Orion BMS for fault reporting and contactor control.
- Label all HV components and enclosures with permanent warning decals.

### Step 6: Initial Power-On and Testing
- Recheck all connections for correct polarity and secure terminations.
- Connect service plug and activate pre-charge circuit.
- Measure voltage on HV bus and verify proper rise profile (pre-charge curve).
- Close main contactor via Orion BMS logic and confirm stable operation.

---

## Safety and Post-Work Procedures

- Deactivate HV system after testing using safe shutdown procedure.
- Record voltage and system state at each testing step.
- Label all new components clearly.
- Document all wiring diagrams, fuse ratings, and configuration files.

---

## Outcomes and Next Steps

At the completion of this stage, the vehicle should have full HV and LV distribution operational, with verified outputs from charger and DC-DC systems.

**Follow-up actions:**

- Review electrical integration with VASS engineer if required.
- Confirm fault codes and system status via Orion BMS and CAN logs.
- Proceed to Stage 7: CAN Bus Integration & Spoofing.

