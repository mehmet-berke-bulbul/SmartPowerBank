# 01 — System Requirements

## 1. Project purpose

Design a USB-C rechargeable powerbank that can fast-charge compatible phones and USB-C devices while monitoring battery state, temperature, power flow, and protection conditions.

## 2. Preliminary engineering targets

| Parameter | Target | Status |
|---|---:|---|
| Battery topology | 2S4P Li-ion | Proposed |
| Cell family | ASPİLSAN 18650 series | Exact part number pending |
| Nominal energy | ~80 Wh | Planning target |
| USB-C ports | 1, bidirectional | Proposed |
| USB-C input | PD, up to 60 W | Target |
| USB-C output | PD/PPS, up to 45 W | Target |
| Display | I²C OLED | Proposed |
| MCU | STM32 family | Proposed |
| PCB | 4 layers | Target |
| Cell balancing | Passive | Proposed |
| Thermal sensing | Battery NTC + power-stage NTC | Required |

## 3. Required protection functions

- Overcharge protection
- Over-discharge protection
- Charge overcurrent protection
- Discharge overcurrent protection
- Short-circuit protection
- Battery overtemperature / undertemperature protection
- Power-stage overtemperature protection
- USB-C ESD protection
- Reverse-current / reverse-power-path protection
- Controlled startup and fault reporting

## 4. Display information

- State of charge (percentage)
- Pack voltage
- Charge/discharge current
- Instantaneous input or output power
- Battery temperature
- USB-C role: charging / discharging / idle
- PD/PPS active status
- Active fault code, if present

## 5. Non-goals for Revision A

- Wireless charging
- Multiple USB output ports
- Active balancing
- Wi-Fi / Bluetooth telemetry
- Final commercial enclosure
- Certified consumer-product compliance

## 6. Open decisions

| Decision | Why it is open |
|---|---|
| Exact cell part number | Datasheet, availability, discharge current and pack dimensions must be verified |
| PD controller | Need to compare PPS support, configurability, availability, firmware needs |
| Charger / buck-boost IC | Need to compare 2S support, reverse mode, external FET needs, thermal performance |
| BMS AFE | Need to compare balancing, current measurement, protection, package and sourcing |
| OLED size | Depends on enclosure and UI layout |
| Output power profile | Must be constrained by thermal design, cable limits and battery current |
