# Servo-Tester
# Servo Tester

A simple standalone circuit for testing hobby servo motors by generating an adjustable PWM signal, without needing a microcontroller.

![3D View](images/3d-view.png)

## Overview

This circuit generates a variable-width PWM pulse (typically ~50Hz, 1ms–2ms pulse width) to drive a standard hobby servo, letting you manually sweep it or center it using a potentiometer — useful for testing, calibrating, or centering servos before installing them in a project.

## Circuit Description

*(Adjust the table below to match your actual component values)*

| Component | Value | Function |
|---|---|---|
| U1 | NE555 / LM555 | Astable/monostable oscillator generating the PWM signal |
| R1 | ~10kΩ (fixed) | Timing resistor |
| RV1 | 10kΩ Potentiometer | Adjusts pulse width (servo position) |
| C1 | ~10nF–100nF | Timing capacitor (sets base pulse frequency) |
| C2 | 10µF | Power supply decoupling capacitor |
| J1 | 3-pin header (Signal, VCC, GND) | Servo output connector |
| J2 | Screw Terminal / DC Jack | Power input (typically 4.8V–6V) |

## Schematic

![Schematic](images/schematic.png)

## PCB Layout

![PCB Layout](images/pcb-layout.png)

## Files

- `*.kicad_pro`, `*.kicad_sch`, `*.kicad_pcb` — KiCad project, schematic, and PCB layout files
- `gerbers/` — Fabrication files (Gerber + drill files) ready to send to a PCB manufacturer
- `images/` — Renders and screenshots of the schematic, PCB, and 3D model

## How to Use

1. Open `Servo-Tester.kicad_pro` in KiCad to view or edit the schematic and PCB.
2. To manufacture the board, send the contents of `gerbers/` to your preferred PCB fab (e.g. JLCPCB, PCBWay).
3. Connect a servo to the 3-pin output header (matching Signal/VCC/GND orientation to your servo's connector).
4. Power the board with 4.8V–6V DC.
5. Turn the potentiometer to sweep the servo from one end to the other, or center it to find the servo's neutral position.

## Notes

- Double-check your servo's signal pin orientation before connecting — reversed polarity can damage the servo or the tester.
- If using a 555 timer in astable mode, verify your R/C values produce a ~50Hz signal with a 1ms–2ms high pulse range (standard servo PWM range) using an oscilloscope or logic analyzer if available.
- A small heatsink or careful current limiting isn't usually necessary for a single small servo, but avoid powering multiple/large servos directly from this board without a beefier supply.

## License

Feel free to specify a license here (e.g. MIT, CERN-OHL) if you'd like others to reuse this design.
