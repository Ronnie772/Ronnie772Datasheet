---
title: Module Power Budget
---

## Overview

The power budget analysis evaluates the current and voltage requirements of all major active components in the system to ensure that the selected power sources and voltage regulators can safely supply sufficient power. The primary active devices considered include the PIC18F57Q83 microcontroller, IFX9201SGAUMA1 motor driver, two Pololu 2371 DC motors, and the MPLAB SNAP programmer. Each component was assigned to an appropriate power rail based on its operating voltage requirements.

The system uses three main power rails: 3.3V, 6V, and 12V. The 3.3V rail powers the microcontroller and logic components, with a total estimated current requirement of 2000 mA in total. These rails are supplied by voltage regulators outputting 2000mA on the 3.3V rail which is more than enough for the 500mA requirement and 1500mA on the 6V rail which is quite adequate for the 1474mA requirement. The margines of saftey ensure sufficient headroom for reliable operation.

The 12V battery serves as the primary external power source, supplying power to the voltage regulators that generate the lower voltage rails. After accounting for all component loads and safety margins, the system remains within the current capabilities of the selected regulators and battery, leaving additional current capacity available for safe operation and potential future expansion.  
  
  <img width="1924" height="736" alt="image" src="https://github.com/user-attachments/assets/61fc266f-762a-4a68-a20f-353bfcfd1c20" />
  <img width="1928" height="535" alt="image" src="https://github.com/user-attachments/assets/d2e20c34-8e2d-48d4-8a20-cef7f832a270" />
  <img width="1924" height="193" alt="image" src="https://github.com/user-attachments/assets/47dcf3d5-278e-42b0-a281-cca54362857e" />

The Power Budget as a PDF download is available [*here*](https://github.com/user-attachments/files/27379409/Power_Budget_.final.pdf)
<br>
For Exel click [*here*](https://github.com/user-attachments/files/27379361/Power_Budget_.final.xlsx)
