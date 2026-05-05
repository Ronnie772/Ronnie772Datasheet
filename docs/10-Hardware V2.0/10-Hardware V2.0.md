---
title: Hardware V2.0
tags:
- tag1
- tag2
---

## Overview
This page discusses the proposed improvements for a second hardware revision of the **Amphibot** actuator subsystem PCB. The current design successfully fulfilled the core requirements of the EGR 314 project, but through the process of building, testing, and debugging the board, several areas were identified where the hardware could be made more robust, more capable, and easier to integrate with the rest of the Amphibot system.

---

## Improvement 1: Corrected Team Communication Header Footprints

One of the most significant issues encountered during the assembly and testing phase of the current PCB was the footprint selection for the **team communication headers**. The footprints used in V1 were too small to accommodate the physical connectors directly, which required the use of **jumper wires**. While this did not cause any electrical issues and the system functioned correctly, it was an unnecessary inconvenience during integration and made the board look less polished than intended.

In **V2.0**, the communication header footprints would be updated to correctly match the physical connectors used across all team boards, eliminating the need for jumper wire workarounds and allowing the connectors to seat directly on the PCB as intended. Beyond footprint correction, the connector placement would also be revisited to position the communication headers along a consistent edge of the board, aligned with the orientation used by the other team subsystems. This would allow all boards to be stacked or mounted side-by-side in the chassis with straight, short wire runs rather than the longer, crossed cables that the current layout requires.


---

## Improvement 2: Corrected L7806ABD2T 6V voltage regulator Footprint


A second footprint issue was discovered with the **L7806ABD2T 6V voltage regulator**. The footprint provided by the **DigiKey** component link turned out to be incorrect and did not match the actual physical dimensions of the component. This required additional rework during assembly to fit the part to the board. In V2.0, every component footprint would be **manually verified against the manufacturer's datasheet** before the design is sent for fabrication, rather than relying solely on footprints pulled from supplier links. This is a lesson that I would apply to all future PCB designs.

---

## Improvement 3: Speed Control via UART Communication

The current firmware supports three discrete motor states — **forward (FWD)**, **reverse (RES)**, and **stop (STP)**  delivered as fixed SPI bytes to the **IFX9201SGAUMA1** motor driver. While this is sufficient for basic directional control, it provides no ability to vary motor speed dynamically. In the current system, speed is fixed at initialization and cannot be adjusted by the HMI or any other subsystem over UART without a firmware rewrite.

In **V2.0**, the UART communication protocol would be extended to include **variable speed commands**, allowing the controlling subsystem to send a target speed value as part of the message payload. For example, a message formatted as `AZMRSPD050YB` could command the motor to run at 50% duty cycle, with the numeric value parsed by the PIC and used to update the **duty cycle register** in real time. This would make the actuator subsystem far more responsive and versatile. the Amphibot could accelerate gradually, slow down before a turn, or modulate speed based on sensor feedback from other subsystems.

---

## Improvement 4: Four-Motor Architecture for Full Amphibot Actuation Coverage

The most substantial architectural change proposed for V2.0 is the expansion from a **two-motor** to a **four-motor** design. The Amphibot V1 robot requires four independently controlled DC motors two for the primary drive wheels and two for the propellers.

By designing V2.0 around **four motor channels**, all actuation for the Amphibot could be centralized on a single PCB. This would require adding a two more **IFX9201SGAUMA1** H-bridge motor drivers, additional **CSN** and **DIR** pin assignments on the **PIC18F57Q83**, and additional motor output connectors. The PIC18F57Q83 has sufficient I/O to support this expansion without requiring a microcontroller change and the additional GPIO pins are already present and were unused in V1.

The power distribution network would also need to be scaled accordingly. The **L7806ABD2T** 6V regulator and its associated filtering capacitors would need to be re-evaluated to ensure they can supply the increased current demand of four motors operating simultaneously. Depending on the worst-case current draw, this might require upgrading to a higher-current 6V regulator or distributing the motor supply across two separate regulation stages. The **power budget** would be recalculated in V2.0 to account for all four motors at full load, and the fuse rating would be updated to match.

---

## Summary of V2.0 Changes

| Change | Reason |
|---|---|
| Corrected communication header footprints | Eliminate assembly issues and improve inter-board integration |
| Corrected L7806ABD2T Footprint | Eliminating rework during assembly |
| Speed control via UART | Enable dynamic motor speed for smoother and more responsive actuation |
| Four-motor architecture | Cover all Amphibot actuation requirements on a single PCB |

These four improvements together would result in a PCB that is easier to assemble, more tightly integrated with the Amphibot system, and significantly more capable in terms of motor control flexibility and coverage.
