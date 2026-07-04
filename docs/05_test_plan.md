# 05 — Test Plan (Draft)

## Before battery connection

- ERC check completed
- DRC check completed
- Correct connector pinout verified
- No short between BAT+, GND, VBUS and logic rails
- Bench supply current limit set low
- Power rails measured independently
- USB-C CC behavior checked
- No abnormal hot components

## Power-stage checks

- No-load startup
- Input charge mode
- 5 V output mode
- PD contract detection
- 9 V / 12 V / 15 V / 20 V profile checks
- Output transient load response
- 45 W thermal soak test
- Short-circuit protection test using a controlled setup

## Battery/BMS checks

- Cell-group voltage readings
- NTC temperature readings
- Overvoltage cutoff
- Undervoltage cutoff
- Charge overcurrent cutoff
- Discharge overcurrent cutoff
- Balancing enable/disable criteria
- Fault reporting to OLED

## Documentation evidence

Save screenshots, oscilloscope plots, thermal images, test tables and known limitations under `assets/`.
