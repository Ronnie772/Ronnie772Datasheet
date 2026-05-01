---
title: Module PCB
---

## Overview

This PCB implements the motor control subsystem and microcontroller interface for the Amphibot V1. Its purpose is to allow bidirectional control of DC motors through an H-bridge driver, and integrate the PIC microcontroller with switches, and debugging interfaces. The board receives a +12V input, which powers the motors and is regulated to 3.3 V for the microcontroller and motor driver's logic and 6 V for the motors.

The PIC microcontroller acts as the central controller, sending signals to the H-bridge motor driver that drives the DC motors connected through the Motor-RSC connectors.

Additional headers (J2, J3) allow external sensors or subsystems to connect to the microcontroller, while SW1 and SW2 provide manual override inputs for testing or control.

 <img width="1253" height="1118" alt="image" src="https://github.com/user-attachments/assets/75295e3c-6e46-45c3-9508-8da47bf5e21f" />



**Figure #1:** Showing the acuator subsystem PCB.

 <img width="2559" height="1502" alt="image" src="https://github.com/user-attachments/assets/655597bb-76fd-47a7-829e-176c55dc1d77" />


**Figure #2:** Showing the PCB's DRC check.



## Resouces

The PCB as a PDF download is available [*here*](https://github.com/user-attachments/files/26040856/all.layers.%2B.DRC.check-v2.pdf)
and the gbr&drl files are available to download [*here*](https://github.com/user-attachments/files/27269319/JLC_v3.zip)

 


