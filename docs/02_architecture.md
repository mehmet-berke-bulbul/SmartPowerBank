# 02 — System Architecture

## Functional block diagram

```text
                   ┌──────────────────────────┐
                   │        USB-C Port        │
                   │  PD/PPS + DRP operation  │
                   └────────────┬─────────────┘
                                │
                   ┌────────────▼─────────────┐
                   │ ESD / CC / VBUS Protection│
                   └────────────┬─────────────┘
                                │
                   ┌────────────▼─────────────┐
                   │ USB-C PD Controller       │
                   │ Role + contract handling  │
                   └────────────┬─────────────┘
                                │
                   ┌────────────▼─────────────┐
                   │ Bidirectional Charger /   │
                   │ Buck-Boost Power Stage    │
                   └────────────┬─────────────┘
                                │
                   ┌────────────▼─────────────┐
                   │ BMS + Current Shunt +     │
                   │ Charge/Discharge MOSFETs  │
                   └────────────┬─────────────┘
                                │
                    ┌───────────▼───────────┐
                    │ 2S4P Li-ion Battery   │
                    │ 2 monitored cell groups│
                    └───────────┬───────────┘
                                │
             ┌──────────────────▼──────────────────┐
             │ BMS AFE + STM32 + OLED + NTC Sensors │
             └──────────────────────────────────────┘
```

## Design principle

The USB-C PD controller handles protocol negotiation. The charger/power-stage IC controls bidirectional energy conversion. The BMS subsystem independently monitors battery safety. The STM32 is responsible for UI, logging, higher-level policies, and later IoT expansion.

## Safety separation

- Battery protection must remain functional even if firmware crashes.
- The MCU must not be the only element deciding short-circuit, overcurrent or overtemperature shutdown.
- High-current switching loops must stay physically compact and separated from sensitive analog sensing paths.
- USB-C connector protection, PD control, power stage, BMS sensing and MCU UI should be represented as separate KiCad sheets.
