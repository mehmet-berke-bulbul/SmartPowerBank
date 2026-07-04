# SmartPowerBank — USB-C PD/PPS Powerbank + Smart BMS

A portfolio-grade hardware project: a 2S4P Li-ion powerbank architecture with USB-C PD/PPS, battery protection, measurement, thermal safety, display UI, and an STM32-based control layer.

> **Project state:** Architecture and requirements phase  
> **Hardware status:** Not yet designed  
> **Important:** Component selections are preliminary until datasheet review, availability checks, simulations, and schematic review are completed.

## Target concept

- Battery topology: **2S4P Li-ion**
- Energy target: approximately **80 Wh class**
- USB-C: **single bidirectional USB-C port**
- Input target: **USB-C PD up to 60 W**
- Output target: **USB-C PD/PPS up to 45 W**
- Battery features: cell-group voltage monitoring, current sensing, NTC temperature monitoring, protection, passive balancing
- User interface: compact OLED display + button(s)
- Controller: STM32 family MCU
- PCB target: 4 layers, high-current power planes, thermal-aware placement

## Repository map

- `docs/` — requirements, architecture, decisions, test plans
- `hardware/kicad/` — KiCad project and hierarchical schematic
- `hardware/datasheets/` — component datasheets
- `hardware/reference_designs/` — vendor app notes and reference circuits
- `hardware/bom/` — BOM, sourcing notes, alternates
- `firmware/` — STM32 firmware
- `simulations/` — LTspice / calculations / thermal checks
- `assets/` — diagrams, screenshots, photos
- `manufacturing/` — Gerbers, drill files, assembly files (later)

## Design workflow

1. Freeze system requirements
2. Compare and select main ICs
3. Create power budget and operating profiles
4. Draw hierarchical KiCad schematic
5. Perform ERC and design review
6. Create PCB stack-up and placement
7. Route high-current and switching loops
8. Perform DRC, manufacturing checks, and BOM review
9. Prepare firmware structure and test plan
10. Publish design documentation

## Current next task

Create the KiCad project under `hardware/kicad/` with the name:

`SmartPowerBank`

Then create the hierarchical sheets listed in `hardware/kicad/SHEET_PLAN.md`.
