# 06 — Schematic Rules

## General

- Every IC must have local decoupling capacitors placed according to its datasheet.
- Use named nets, not long wires across the sheet.
- Keep power domains clearly named: `VBUS`, `BAT+`, `PACK+`, `SYS`, `3V3`, `GND`.
- Use dedicated net labels for cell nodes: `CELL0`, `CELL1`, `CELL2`.
- Do not connect unrelated I²C devices until bus ownership and address conflicts are reviewed.
- Add test points for all critical rails and signals.

## High-current sections

- Clearly mark high-current nets.
- Include current direction annotations.
- Use Kelvin connections for the current shunt sensing lines.
- Keep switching-node nets short and isolated.
- Document every fuse, TVS, MOSFET and protection threshold.

## Review checklist per sheet

- Pin 1 orientation checked
- Absolute maximum ratings checked
- Recommended operating conditions checked
- Decoupling values and voltage ratings checked
- Pull-up / pull-down states checked
- Unused pins handled according to datasheet
- Thermal pad connection and via strategy noted
- Footprint availability verified
