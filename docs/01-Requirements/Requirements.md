---
title: Module's Requirements
---

## Module Requirements

Actuator Control Module Overview (PIC)

The Actuator Control module is responsible for executing motor commands and ensuring safe, responsive movement of the robot. Implemented on a PIC microcontroller, this module receives motion and safety commands over UART and generates PWM signals to drive the motor controller, enabling controlled forward and backward motion.

This module prioritizes safety and fault handling, including rapid emergency stop response, overcurrent protection, and thermal shutdown. In the event of a fault or loss of communication, the system transitions to a safe state by disabling motor output, ensuring predictable and reliable behavior during operation and demonstrations.



| **Requirement Description** | **Measure of<br> Threshold** | **Target<br>Measure** |**Stretch<br>Requirement<br>(Y-N)**|
|-----------------------------| ----------------- | ----------------- | :-----: |
| PIC microcontroller operation | Execute firmware | Motors respond correctly to PWM | No |
| Motor control functionality | Forward and backward motion | Smooth, speed controlled driving | No |
| Motor driver interface | Driver responds to control signals | PWM control with current limiting | No |
| Emergency stop response | Motors stop within 1 second | Motors stop within 250 ms | Yes |
| Overcurrent protection | Warning issued | Automatic motor shutdown | No |
| Thermal protection | Warning issued | Automatic motor shutdown | No |
| UART communication | Basic motor state messaging | Structured motor telemetry reporting | Yes |
| Safe-state behavior | Motors stop on fault | Guaranteed motor disable on fault or comms loss | No |
| System reset behavior | Manual reset required | Fast recovery for repeated demos | No |

