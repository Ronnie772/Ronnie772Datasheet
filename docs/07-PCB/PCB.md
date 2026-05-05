---
title: Module PCB
---

## Overview

This PCB represents the **actuator subsystem** for the **Amphibot**, designed for EGR 314. The system is powered by a **12V 7Ah battery**, which feeds two voltage regulation stages: an **AP63203WU-7** switching regulator that steps down to **3.3V** for the PIC18F57Q83 microcontroller and motor driver logic, and an **L7806ABD2T** linear regulator that provides a stable **6V** supply to the motors through the **IFX9201SGAUMA1** H-bridge motor driver.

The **PIC18F57Q83** serves as the central controller, managing bidirectional DC motor control and speed regulation through dedicated I/O pins. **CSN pins** output signals to the motor drivers to regulate motor speed, while **DIR pins** send digital HIGH/LOW signals to control the direction of rotation. The PIC is programmed via a **Microchip SNAP programmer** using the **ICSP interface**.

Two **override/system check buttons (SW1, SW2)** are included to support manual testing and diagnostic procedures, allowing independent verification of motor driver functionality and motor behavior outside of firmware control. Additional headers **(J2, J3)** provide connection points for external sensors or subsystems.

 <img width="2278" height="2434" alt="pcb_populated_front" src="https://github.com/user-attachments/assets/3eafea52-fcfc-4e00-8b27-18c7fb451db6" />

**Figure #1:** Showing the complete populated acuator PCB (front).

 <img width="3372" height="3001" alt="pcb_populated_back" src="https://github.com/user-attachments/assets/b6d4223b-14cc-4fda-ab0e-e31fba72da12" />

**Figure #2:** Showing the complete populated acuator PCB (back).

<img width="2197" height="1958" alt="pcb_unpopulated_front" src="https://github.com/user-attachments/assets/f4d908ab-5b73-4e5c-ad95-05408f39a475" />


**Figure #3:** Showing the unpopulated acuator PCB (front).

 <img width="2864" height="2555" alt="pcb_unpopulated_back" src="https://github.com/user-attachments/assets/20e32781-33f1-422d-98d7-f1546b665e78" />


**Figure #4:** Showing the unpopulated acuator PCB (front).

 <img width="1253" height="1118" alt="image" src="https://github.com/user-attachments/assets/75295e3c-6e46-45c3-9508-8da47bf5e21f" />

**Figure #5:** Showing the complete acuator PCB (ECAD).

<img width="1314" height="1166" alt="front" src="https://github.com/user-attachments/assets/dbc32f18-ff31-48f3-8764-327ba9fc3887" />

**Figure #6:** Showing the Front Copper of the PCB.

<img width="1318" height="1172" alt="back" src="https://github.com/user-attachments/assets/552f5820-e482-4f7b-b587-566258fb459f" />

**Figure #7:** Showing the Back Copper of the PCB.

 <img width="2408" height="1188" alt="DRC-check" src="https://github.com/user-attachments/assets/079b92a6-7b5e-4ee1-b235-ea23fbb11cb7" />

**Figure #8:** Showing the PCB's DRC check.



## Resouces

The PCB as a PDF download is available [*here*](https://github.com/user-attachments/files/27269400/all_layers.pdf.pdf).
The gbr&drl files are available to download [*here*](https://github.com/user-attachments/files/27269319/JLC_v3.zip).
The project zip file is available [*here*](https://github.com/user-attachments/files/27381323/egr314-design-RSC.v2.zip.zip)



