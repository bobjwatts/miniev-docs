# Troubleshooting & Technical Insights

This section captures problems encountered during the EV conversion process, how they were diagnosed, and the solutions applied. It also includes technical notes, calibration details, and design insights that may help in future maintenance or support other converters.

---

## Common Issues & Fixes

### 🚫 Inverter Not Responding
**Symptom:** No motor movement during bench test  
**Diagnosis:** Incorrect pre-charge timing; contactor not closing  
**Solution:** Adjust OpenInverter settings and verify correct pre-charge resistor value

---

### ⚠️ BMS Reporting Fault Codes
**Symptom:** Orion BMS displays cell imbalance error  
**Diagnosis:** One Leaf module had lower voltage  
**Solution:** Manually top-balanced module before integration

---

### 🌡 Cabin Heater Tripping Fuse
**Symptom:** Heater cuts out after 5–10 seconds  
**Diagnosis:** Undersized fuse for startup current  
**Solution:** Upgraded to correct rated fuse per heater spec sheet

---

## Technical Notes

- OpenInverter throttle configuration used **dual analog Leaf pedal**
- CAN spoofing uses **ESP32 with MCP2515**, mapped Mini RPM, speed, SOC
- 12V system fused into existing Mini power distribution
- Chrono Pack repurposed: coolant temp gauge shows inverter temp; fuel gauge shows SOC

---

## Lessons Learned

- Confirm all donor components on the bench *before* disassembling the car
- Take photos and label everything during disassembly
- CAN reverse-engineering is easier if you simulate road conditions (e.g. moving wheels on jacks)
- Pre-charge logic must be tested under load

