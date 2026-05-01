---
title: Module PCB
---

## Overview

This PCB implements the motor control subsystem and microcontroller interface for the Amphibot V1. Its purpose is to allow bidirectional control of DC motors through an H-bridge driver, and integrate the PIC microcontroller with switches, and debugging interfaces. The board receives a +12V input, which powers the motors and is regulated to 3.3 V for the microcontroller and motor driver's logic and 6 V for the motors.

The PIC microcontroller acts as the central controller, sending signals to the H-bridge motor driver that drives the DC motors connected through the Motor-RSC connectors.

Additional headers (J2, J3) allow external sensors or subsystems to connect to the microcontroller, while SW1 and SW2 provide manual override inputs for testing or control.

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


