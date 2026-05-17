# NFC Reader With Relay

This project is an ESP32-based NFC reader module designed to detect ISO 14443A-compatible NFC tags and control an external device using a relay. The system uses the TRF7970A NFC transceiver for short-range communication and an ESP32-PICO-D4 microcontroller for tag reading, relay control, and future wireless expansion. When a compatible NFC tag is placed near the antenna, the ESP32 reads the tag UID and toggles the relay. This design can be adapted for access control, door locks, motor control, automation systems, or IoT-based device switching.

## Key Features
 
- ISO 14443A NFC tag detection
- ESP32-PICO-D4 based control
- TRF7970A NFC transceiver
- Relay output for external device switching
- LED indicator outputs through ESP32 GPIOs
- 10V to 24V input power range
- 12V, 5V, and 3.3V regulated power rails
- NFC antenna tuning at 13.56 MHz
- SPI communication between ESP32 and TRF7970A
- 4-layer PCB design with RF-aware layout

## Major Components

| Component | Function |
|---|---|
| ESP32-PICO-D4 | Wi-Fi/Bluetooth microcontroller for tag reading and relay control |
| TRF7970A | NFC transceiver and analog front end |
| LM5176 | Buck-boost converter for regulated 12V rail |
| LM2576S-5.0 | 5V regulator |
| MIC2940A-3.3 | 3.3V regulator for logic and NFC circuitry |
| Relay Driver | Controls external load when a valid NFC tag is detected |
| LED Headers | Visual indication for tag read or relay status |

## Design Approach

The board is built around the ESP32-PICO-D4 and TRF7970A. The TRF7970A handles NFC communication and drives the external antenna through a matching network. The ESP32 communicates with the NFC transceiver over SPI, reads the tag UID, and toggles the relay through a GPIO pin.

The power architecture uses a wide 10V to 24V input and generates the required 12V, 5V, and 3.3V rails. The PCB layout uses a 4-layer stack-up to improve grounding, power distribution, EMI control, and RF performance. Special attention is given to antenna routing, ground planes, decoupling capacitors, and separation between RF and relay sections.

## Project Files

- [Schematic Diagram](https://github.com/harinibabu63/NFC-reader-with-relay/blob/main/NFC%20reader%20with%20relay%20schematic.png)
- [PCB Layout](https://github.com/harinibabu63/NFC-reader-with-relay/blob/main/NFC%20reader%20with%20relay%20PCB.png)
- [FAB Notes](https://github.com/harinibabu63/NFC-reader-with-relay/blob/main/FAB%20Notes%20NFC%20reader%20with%20relay.png)
- [Assembly Notes](https://github.com/harinibabu63/NFC-reader-with-relay/blob/main/Assembly%20Notes.png)

## What I Learned

- NFC reader circuit design
- ESP32-based hardware control
- TRF7970A NFC transceiver integration
- SPI communication between microcontroller and NFC IC
- Relay driver circuit design
- Multi-rail power supply planning
- 4-layer PCB layout strategy
- RF antenna tuning and 13.56 MHz layout considerations
- EMI reduction and RF/digital section separation
