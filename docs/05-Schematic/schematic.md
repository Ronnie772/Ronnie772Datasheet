---
title: Module Schematic
---

## Overview

This schematic represents the motor subsystem controlled by a PIC18F57Q83 microcontroller. The system is powered by a 12V 7Ah battery, which supplies energy to two voltage regulation stages that provide stable power to the control electronics and motors. A 3.3V switching regulator (AP63203WU-7) generates the logic-level supply used by the microcontroller and a 6V regulator (L7806ABD2T) that powers the motors through the motor driver (IFX9201SGAUMA1), this ensures safe and consistent operation of the control system.

The PIC serves as the central controller and communicates with the system through several digital and PWM-capable I/O pins. The device is programmed through a Microchip SNAP programmer using the ICSP interface. Two CSN pins send signals to the motor drivers to regulate motor speed, while DIR pins send 1 or 0 digital signal to control the direction of motor rotation.

Two override/system check buttons are included to support manual testing and diagnostic procedures. These inputs provide digital signals that allow the system to verify motor driver functionality and motor behavior independently of the firmware.


  <img width="2328" height="956" alt="image" src="https://github.com/user-attachments/assets/1863398b-a081-4a97-9050-074ac19685ac" />



**Figure #1:** Showing the acuator subsystem schematic.


## Resouces

The schematic as a PDF download is available [*here*](https://github.com/user-attachments/files/27269256/egr314-design-RSC.v2.pdf), and the Zip folder of the project [*here*](https://github.com/user-attachments/files/27269275/egr314-design-RSC.v2.zip.zip)
 
