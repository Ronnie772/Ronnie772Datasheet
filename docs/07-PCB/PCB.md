---
title: Module PCB
---

## Overview

This schematic defines the complete motor control subsystem, including power regulation, microcontroller control logic, override inputs, and the H-bridge motor driver. The design distributes power from a 12 V battery to both the control electronics and the motors while maintaining stable operating voltages for each subsystem.

The power supply section generates the required regulated rails. A 3.3 V switching regulator (AP63203WU-7) provides the logic supply used by the PIC18F47K42 microcontroller, control inputs, and other digital circuitry. A separate 6 V linear regulator (L7806ABD2T) supplies the motor driver’s VM input and the motors themselves. Decoupling capacitors are included around the regulators and major ICs to reduce electrical noise and ensure stable voltage levels.

The PIC18F47K42 microcontroller acts as the central controller for the subsystem. It is programmed through the Microchip SNAP ICSP interface and operates from the regulated 3.3 V rail. The microcontroller generates PWM outputs for motor speed control and digital signals that determine motor direction. Additional header connections allow communication with other subsystems and provide access for debugging and expansion.

Two override switches are included to support testing and system safety checks. These switches provide 3.3 V digital signals that can override or supplement the microcontroller control inputs during diagnostic operation.

The motor driver (H-bridge) receives PWM and digital control signals from the microcontroller and converts them into higher-current outputs capable of driving the two DC motors. Bypass capacitors near the driver help suppress switching noise produced by the motors.

Overall, this schematic integrates regulated power distribution, microcontroller-based control, and hardware override capability to provide reliable bidirectional motor control while supporting system testing and integration with the broader platform

  <img width="952" height="681" alt="image" src="https://github.com/user-attachments/assets/f562c672-f9f8-41f9-825b-3bf0c1d8c4fd" />

  <img width="2557" height="1503" alt="image" src="https://github.com/user-attachments/assets/48a9f149-6d5a-4f1e-bf99-ca8b8626ca2f" />



**Figure #1:** Showing the acuator subsystem PCB.


## Resouces

The PCb gbr&drl files are available to download [*here*](https://github.com/user-attachments/files/25830912/gbr.drl_files_pcb.egr314.zip-file.zip)
 
 


