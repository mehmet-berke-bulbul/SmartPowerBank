# 03 — Power Budget and First Calculations

## Initial pack assumption

This is a planning calculation only. Replace values after the exact ASPİLSAN cell is selected.

```text
Topology: 2S4P
Assumed cell nominal voltage: 3.6 V
Assumed cell capacity: 2.7 Ah

Pack nominal voltage = 2 × 3.6 V = 7.2 V
Pack capacity = 4 × 2.7 Ah = 10.8 Ah
Nominal pack energy = 7.2 V × 10.8 Ah = 77.76 Wh
```

## 45 W output current estimate

At a low pack voltage around 6.4 V, assuming 90% conversion efficiency:

```text
Battery input power ≈ 45 W / 0.90 = 50 W
Battery current ≈ 50 W / 6.4 V = 7.8 A
Current per parallel cell ≈ 7.8 A / 4 = 1.95 A
```

This is a key design point: the battery path, MOSFETs, shunt, inductor, copper planes, connector and thermal design must safely sustain the corresponding current.

## Preliminary USB-C profiles

| Mode | Voltage | Current | Power |
|---|---:|---:|---:|
| Default | 5 V | 3 A | 15 W |
| PD | 9 V | 3 A | 27 W |
| PD | 12 V | 3 A | 36 W |
| PD | 15 V | 3 A | 45 W |
| PD | 20 V | 2.25 A | 45 W |
| PPS | Variable | Profile dependent | Up to 45 W target |

## To calculate after IC selection

- Peak inductor current
- MOSFET conduction and switching losses
- Shunt resistor power and measurement range
- Input capacitor RMS current
- Output capacitor ripple current
- Thermal dissipation at 45 W continuous output
- Battery runtime at 5 W, 15 W, 27 W and 45 W loads
