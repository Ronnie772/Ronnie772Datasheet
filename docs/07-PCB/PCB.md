---
title: Module PCB
---

## Overview

This PCB represents the **actuator subsystem** for the **Amphibot**, designed for EGR 314. The system is powered by a **12V 7Ah battery**, which feeds two voltage regulation stages: an **AP63203WU-7** switching regulator that steps down to **3.3V** for the PIC18F57Q83 microcontroller and motor driver logic, and an **L7806ABD2T** linear regulator that provides a stable **6V** supply to the motors through the **IFX9201SGAUMA1** H-bridge motor driver.

The **PIC18F57Q83** serves as the central controller, managing bidirectional DC motor control and speed regulation through dedicated I/O pins. **CSN pins** output signals to the motor drivers to regulate motor speed, while **DIR pins** send digital HIGH/LOW signals to control the direction of rotation. The PIC is programmed via a **Microchip SNAP programmer** using the **ICSP interface**.

Two **override/system check buttons (SW1, SW2)** are included to support manual testing and diagnostic procedures, allowing independent verification of motor driver functionality and motor behavior outside of firmware control. Additional headers **(J2, J3)** provide connection points for external sensors or subsystems.

 <img width="1253" height="1118" alt="image" src="https://github.com/user-attachments/assets/75295e3c-6e46-45c3-9508-8da47bf5e21f" />

**Figure #1:** Showing the complete acuator PCB.

<img width="1314" height="1166" alt="front" src="https://github.com/user-attachments/assets/dbc32f18-ff31-48f3-8764-327ba9fc3887" />

**Figure #2:** Showing the Front Copper of the PCB.

<img width="1318" height="1172" alt="back" src="https://github.com/user-attachments/assets/552f5820-e482-4f7b-b587-566258fb459f" />

**Figure #3:** Showing the Back Copper of the PCB.

 <img width="2408" height="1188" alt="DRC-check" src="https://github.com/user-attachments/assets/079b92a6-7b5e-4ee1-b235-ea23fbb11cb7" />

**Figure #4:** Showing the PCB's DRC check.



## Resouces

The PCB as a PDF download is available [*here*](https://github.com/user-attachments/files/27269400/all_layers.pdf.pdf).
The gbr&drl files are available to download [*here*](https://github.com/user-attachments/files/27269319/JLC_v3.zip).


