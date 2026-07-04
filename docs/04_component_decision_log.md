# 04 — Component Decision Log

Do not mark a component as final before its datasheet, package, availability, thermal limits and reference design have been reviewed.

| Block | Candidate | Status | Decision criteria |
|---|---|---|---|
| USB-C receptacle | TBD | Open | 5 A rating, footprint, mechanical strength |
| USB-C PD controller | TBD | Open | DRP, PD/PPS, configuration method, sourcing |
| Bidirectional charger | TBD | Open | 2S support, reverse/OTG mode, external FETs, output capability |
| BMS AFE | TBD | Open | 2S support, current sensing, protection, balancing, package |
| Battery MOSFETs | TBD | Open | Rds(on), Vds margin, thermal package, gate drive compatibility |
| Current shunt | TBD | Open | Power rating, TCR, resistance, Kelvin routing |
| MCU | STM32G0 family | Proposed | I²C, ADC, low power, availability, debug support |
| Display | 0.96–1.3 inch I²C OLED | Proposed | 3.3 V operation, size, library support |
| Battery temperature | 10 kΩ NTC | Proposed | BMS/charger compatibility |
| TVS / ESD arrays | TBD | Open | USB-C signal capacitance, surge and ESD rating |

## Decision record format

For each final selection, add:

- Date
- Selected part number
- Alternatives compared
- Why selected
- Key datasheet parameters
- Package/footprint
- Sourcing note
- Risks and mitigations
