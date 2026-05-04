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


Downloadable pdf available [*here*](https://github.com/user-attachments/files/27378867/block-diagram-RSC-EGR314.drawio.pdf)


