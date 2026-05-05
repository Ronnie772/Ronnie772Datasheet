---
title: Module's Block Diagram
tags:
- tag1
- tag2
---

## Overview

This block diagram represents the **motor subsystem** controlled by a **PIC18F57Q83** microcontroller. The system is powered by a **12V 7Ah battery**, which supplies energy to two voltage regulation stages that provide stable power to the control electronics and motors. A **3.3V switching regulator (AP63203WU-7)** generates the logic-level supply used by the microcontroller and a **6V regulator (L7806ABD2T)** that powers the motors through the **motor driver (IFX9201SGAUMA1)**, this ensures safe and consistent operation of the control system.

The **PIC** serves as the central controller and communicates with the system through several digital and **I/O pins**. The device is programmed through a **Microchip SNAP programmer** using the **ICSP interface**. Two **CSN pins** send signals to the motor drivers to regulate motor speed, while **DIR pins** send High/Low digital signal to control the direction of motor rotation.

Two **override/system check buttons** are included to support manual testing and diagnostic procedures. These inputs provide digital signals that allow the system to verify motor driver functionality and motor behavior independently of the firmware.


## Block Diagram 

  <img width="1081" height="652" alt="image" src="https://github.com/user-attachments/assets/f26372dc-6c4e-44e1-be38-3e5efb17fab0" />

## Design Decisions

The block diagram was developed by first identifying the core functional requirements of the motor subsystem: the ability to receive commands over UART, drive two DC motors bidirectionally, and operate reliably from a single battery source. The **PIC18F57Q83** was selected as the central microcontroller because it provides sufficient **PWM and digital I/O pins**, native **SPI and UART peripherals**, and is directly supported by **MPLAB X IDE** and **MCC**, which streamlined firmware development and pin configuration. 

The **12V 7Ah battery** was chosen to provide enough current capacity to drive both motors simultaneously without significant voltage sag. Rather than powering the microcontroller directly from 12V, two separate regulation stages were designed: the **AP63203WU-7** switching regulator steps down to **3.3V** for the logic circuitry, minimizing heat dissipation, while the **L7806ABD2T** provides a stable **6V** rail for the motors through the **IFX9201SGAUMA1** H-bridge driver. This separation ensures that switching noise from the motor driver does not couple into the sensitive microcontroller logic.

The **SPI interface** was chosen to communicate motor commands to the H-bridge driver because it offers faster and more reliable data transfer compared to a simple GPIO toggle approach, allowing precise control over motor direction and speed in a single transaction. The two **override/system check buttons** were included from the start to support hardware-level testing and verification of motor driver behavior independently of firmware, which proved critical during bring-up and debugging.

## Resources

Downloadable pdf available [*here*](https://github.com/user-attachments/files/27378867/block-diagram-RSC-EGR314.drawio.pdf)
zip file of project available [*here*](https://github.com/user-attachments/files/27380395/egr314-design-RSC.v2.zip.zip)

