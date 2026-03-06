---
title: Module Power Budget
---

## Overview

The power budget analysis evaluates the current and voltage requirements of all major active components in the system to ensure that the selected power sources and voltage regulators can safely supply sufficient power. The primary active devices considered include the PIC18F47K42 microcontroller, TB6612FNG motor driver, two Pololu 2371 DC motors, and the MPLAB SNAP programmer. Each component was assigned to an appropriate power rail based on its operating voltage requirements.

The system uses three main power rails: 3.3V, 6V, and 12V. The 3.3V rail powers the microcontroller and logic components, with a total estimated current requirement of 1400 mA, increased to 1750 mA after applying a 25% safety margin. The 6V rail powers the two DC motors, which together require 1340 mA, increasing to 1675 mA with the safety margin. These rails are supplied by voltage regulators capable of providing up to 2000 mA, ensuring sufficient headroom for reliable operation.

The 12V battery serves as the primary external power source, supplying power to the voltage regulators that generate the lower voltage rails. After accounting for all component loads and safety margins, the system remains within the current capabilities of the selected regulators and battery, leaving additional current capacity available for safe operation and potential future expansion.  
  
  
 <img width="1087" height="876" alt="image" src="https://github.com/user-attachments/assets/3f5914a1-f282-4225-b7d3-8371c03f4bf7" />


[Power Budget (egr334).pdf](https://github.com/user-attachments/files/25691557/Power.Budget.egr334.pdf),
[*exel*](https://github.com/user-attachments/files/25802111/Power_Budget_.final.xlsx)


