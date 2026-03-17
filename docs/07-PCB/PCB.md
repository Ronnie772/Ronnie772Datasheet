---
title: Module PCB
---

## Overview

This PCB implements the motor control subsystem and microcontroller interface for the Amphibot V1. Its purpose is to allow bidirectional control of DC motors through an H-bridge driver, and integrate the PIC microcontroller with switches, and debugging interfaces. The board receives a +12V input, which powers the motors and is regulated to 3.3 V for the microcontroller and motor driver's logic and 6 V for the motors.

The PIC microcontroller acts as the central controller, sending signals to the H-bridge motor driver that drives the DC motors connected through the Motor-RSC connectors.

Additional headers (J2, J3) allow external sensors or subsystems to connect to the microcontroller, while SW1 and SW2 provide manual override inputs for testing or control.

  <img width="952" height="681" alt="image" src="https://github.com/user-attachments/assets/f562c672-f9f8-41f9-825b-3bf0c1d8c4fd" />


**Figure #1:** Showing the acuator subsystem PCB.

<img width="2559" height="1502" alt="image" src="https://github.com/user-attachments/assets/ce9f208b-6cf7-4658-9b8b-a797c40a1555" />



**Figure #2:** Showing the PCB's DRC check.


## Resouces

The PCB as a PDF download is available [*here*](https://github.com/user-attachments/files/25831121/all.layers.%2B.DRC.check.of.PCB.pdf)
and the gbr&drl files are available to download [*here*](https://github.com/user-attachments/files/25830912/gbr.drl_files_pcb.egr314.zip-file.zip)
 
 


