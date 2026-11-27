# LED Ring 0603

The custom PCB for the [LED Ring](https://github.com/jszym99/LEDRing) project. The board carries a ring of 72 0603 LEDs, driven by an ATtiny84A and powered from a CR2032 coin cell. An ADXL367 accelerometer on the board lets the firmware react to motion.

![image](LED%20Ring%200603.png)

## Features

- 72 x 0603 LEDs arranged in a ring, Charlieplexed on 9 pins (9 x 8 = 72)
- ATtiny84A microcontroller using its internal oscillator
- ADXL367 3-axis accelerometer connected over I2C, with an interrupt line (`INT0`) to the microcontroller
- Powered by a single cell in a Keystone 3034 1x20 mm battery holder
- 4-layer PCB

## Schematic

The design is hierarchical. The root sheet `LED Ring 0603.kicad_sch` contains four sub-sheets:

| Sheet | File | Contents |
|:---|:---|:---|
| Led Matrix | `ledmatrix.kicad_sch` | The 72 LEDs |
| MCU | `microcontroller.kicad_sch` | ATtiny84A |
| Accelerometer | `accelerometer.kicad_sch` | ADXL367 and the `I2C` and `INT0` signals |
| Power | `power.kicad_sch` | Battery |

A PDF of the schematic is at `PDFs/LED Ring 0603.pdf`.

## PCB

The board layout is in `LED Ring 0603.kicad_pcb`, with a PDF print at `PDFs/LED Ring 0603 PCB.pdf`.

## Notes

- Ensure the 0603 LED footprint polarity matches the part you order before assembly
- The PCB has no dedicated programming connector. Program the microcontroller by attaching a SOIC-14 clip directly to it
- The board is designed for JLCPCB fabrication and assembly, and the design rules in the KiCad project are set to its manufacturing capabilities
- Production files for JLCPCB, generated with the Fabrication Toolkit plugin, are in `production/`. `LED_Ring_0603.zip` is for fabrication, and `bom.csv` and `positions.csv` are for assembly
