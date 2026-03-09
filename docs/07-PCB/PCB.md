---
title: Module PCB
---

## Overview

This PCB implements the motor control subsystem and microcontroller interface for the Amphibot V1. Its purpose is to allow bidirectional control of DC motors through an H-bridge driver, and integrate the PIC microcontroller with switches, and debugging interfaces. The board receives a +12V input, which powers the motors and is regulated to 3.3 V for the microcontroller and logic components using a voltage regulator and filtering capacitors.

The PIC microcontroller acts as the central controller, sending signals to the H-bridge motor driver that drives the DC motors connected through the Motor-RSC connectors.

Additional headers (J2, J3) allow external sensors or subsystems to connect to the microcontroller, while SW1 and SW2 provide manual override inputs for testing or control.

  <img width="952" height="681" alt="image" src="https://github.com/user-attachments/assets/f562c672-f9f8-41f9-825b-3bf0c1d8c4fd" />


**Figure #1:** Showing the acuator subsystem PCB.

  <img width="2557" height="1503" alt="image" src="https://github.com/user-attachments/assets/48a9f149-6d5a-4f1e-bf99-ca8b8626ca2f" />



**Figure #2:** Showing the PCB's DRC check.


## Resouces

The PCb gbr&drl files are available to download [*here*](https://github.com/user-attachments/files/25830912/gbr.drl_files_pcb.egr314.zip-file.zip)
 
 


