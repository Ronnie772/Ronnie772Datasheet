---
title: Reflection
tags:
- tag1
- tag2
---

## Overview

This page reflects on the development of the **Amphibot** actuator subsystem over the course of EGR 314. It reviews what requirements were successfully met, what was missed, and the most important lessons learned throughout the design, fabrication, assembly, and integration process.

---

## Review of Module's Success

### Requirements Met

The actuator subsystem successfully met its core functional requirements. The **PIC18F57Q83** microcontroller was correctly configured and programmed to receive **UART messages** from the HMI subsystem, parse them according to the team's communication protocol, and relay the appropriate **SPI motor commands** to the **IFX9201SGAUMA1** H-bridge driver. Both DC motors responded correctly to forward, reverse, and stop commands, and the system operated reliably from the **12V battery** through the two voltage regulation stages. The **ICSP programming interface** worked as expected with the **Microchip SNAP programmer**, and the **override/system check buttons** functioned correctly for manual testing and diagnostic purposes.

---

## Microcontroller and Module Startup Tips

The following is a list of tips gathered from bringing up the PIC18F57Q83-based actuator subsystem. These are things that would have saved significant time if known earlier:

- **Verify every footprint against the manufacturer's datasheet before ordering** — do not trust supplier-provided footprints blindly, the L7806ABD2T footprint from DigiKey was incorrect and required rework.
- **Double-check connector footprint sizes before fabrication** — a footprint that is even slightly undersized forces jumper wire workarounds that could have been avoided with a quick measurement.
- **Use MCC to configure all peripherals before writing any application code** — configuring SPI, UART, and PWM registers manually from scratch is far slower and more error-prone than using the MCC code generator.
- **Read the datasheet for every component** — the IFX9201SGAUMA1 has specific SPI timing requirements around the CSN pin that must be respected.
- **Test UART communication in isolation before integrating with other subsystems** — use a terminal emulator like Data Visualizer or if using SMD components then use something like an EPS and connect your RX and TX to it to confirm your message format is correct and confirm your UART communication setup before intergrating the code with other functionalities.
- **Start with a simple loopback test** — connecting TX to RX and echoing bytes back is the fastest way to confirm your UART peripheral is configured correctly.

