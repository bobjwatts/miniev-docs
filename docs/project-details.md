# Mini Cooper S EV Conversion – Summary for VASS Engineer

**Base Vehicle:** 
- **2006 Mini Cooper S (R53)**
- Odometer - 180,000 
- Last road worthy 04/2025
- Registration ended 08/2025   
**EV Donor:** 2018 Nissan Leaf (ZE1)  
**Conversion Intent:** Daily road-legal EV, retaining factory safety systems where possible and compliant with NCOP and VicRoads/VASS requirements.

---

## Powertrain

- **Motor:** Nissan Leaf EM57 stack (motor, inverter, reduction gear)
- **Mounting:** Custom mounts to Mini subframe/mounts, securely integrated. Stack height (~440 mm) confirmed to fit under ~550 mm bonnet clearance.
- **Drive Shafts:** Leaf CVs to be adapted or custom shafts fabricated to match Mini hubs.

---

## Electrical Systems

- **VCU:** ZombieVerter (OpenInverter) – manages inverter and Leaf BMS via CAN.
- **Throttle Input:** *Mini’s original accelerator pedal retained* (2-channel Hall effect), wired to ZombieVerter. Avoids custom bracket and maintains factory ergonomics.
- **Gear Selector:** Leaf gear selector retained for PRND input.
- **Charging:** Leaf onboard AC charger used (CHAdeMO removed, possible addition in future). Charging port relocated to factory fuel filler location.
- **12V System:** Leaf DC-DC converter supports vehicle's 12V loads.

---

## HV Battery & BMS

- **Battery Pack:** 40 kWh Leaf Gen 2 modules (SoH 88%), split between front and rear for weight balance.
- **Enclosures:** Custom-fabricated 3 mm aluminum, vented, sealed, fire-resistant, and mounted to reinforced chassis points.
- **BMS:** *Leaf BMS retained*, integrated via ZombieVerter CAN interface.
- **HV Safety:** Leaf contactors, service disconnect, HV fusing, and pre-charge circuit implemented.

---

## Auxiliary Systems

- **Brakes:** Electric vacuum pump replaces ICE vacuum source. Mini’s hydraulic system otherwise retained.
- **Cooling:** Leaf electric pump and radiator cool motor/inverter. Batteries cooled passively (as per Leaf spec).
- **HV Heating (Optional):** PTC coolant heater under evaluation for demisting and cabin heating.

---

## Compliance Overview

- Designed to meet:
  - **NCOP14 – Electric Drive Conversions**
  - **VSB-14 / VSI-8** guidance
  - **Relevant ADRs** for braking, steering, lighting, restraint systems

- Additional compliance considerations:
  - High-voltage isolation and safety
  - Ingress protection and thermal/fire management
  - CAN spoofing compatibility (BMW E46/Mini R53 cluster integration)
  - GVM compliance and post-conversion weight balance

---


## Project Breakdown

**Key Tasks:**

| Milestone                                               | Status               |
|---------------------------------------------------------|----------------------|
| Leaf donor parts procurement & bench-testing            | Completed            |
| Leaf HV battery assesment                               | Completed            |
| Bench test - ZV (ZombieVerter)                          | Completed            |
| Bench test - ZV HV Battery integration                  | Completed            |
| Bench test - ZV Leaf Inverter/Motor Stack integration   | Completed            |
| Mini Cooper Engine removal                              | Not started          |
| Mechanical integration & mounting                       | Not started          |
| Battery box design fabrication                          | Not started          |
| Battery installation & safety checks                    | Not started          |
| Electrical integration                                  | Not started          |
| CAN Bus spoofing and systems testing                    | Not started          |
| Climate control & interior modifications                | Not started          |
| Final systems checks & certification prep               | Not started          |
| ACC Certification completion                            | Not started          |

---



