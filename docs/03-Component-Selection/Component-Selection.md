---
title: Module's Selected Major Components
---

## Module's Selected Major Components

The following sections are the selected major components necessary for  .....

>**For each of the following sections, use <ins>one of the two styles</ins> given near the end. *REMOVE THIS NOTE***

### Power Management

(**remove this note/placeholder**: this is where your 3.3 volt switching regulator, any other needed power regulator, and power source {if applicable} **THAT WERE SELECTED**)

For more details, review the ["Appendix - Component Selection Process - Power Mangement"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#power-management) selection.

### Sensor

(**remove this note/placeholder**: if applicable, this is where your  **SELECTED** sensor is shown. Otherwise, remove this section.)

For more details, review the ["Appendix - Component Selection Process - Sensor"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#sensor) selection.

### Actuator

(**remove this note/placeholder**: if applicable, this is where your **Selected** the actuator items go, which includes both the driver and motor. Otherwise, remove this section.)

For more details, review the ["Appendix - Component Selection Process - Actuator"](https://embedded-systems-design.github.io/EGR314DataSheetTemplate/Appendix/01-Componet-Selection/Component-Selection-Process/#actuator) selection.

-----------


**Motor Driver**

1. DRV8220DRLR 

    <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/9c21f797-13c4-4860-aaec-24c6caca18ed" />

    * $0.77/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/DRV8220DRLR/15295783)
    * [Datasheet](https://www.ti.com/lit/ds/symlink/drv8220.pdf?HQS=dis-dk-null-digikeymode-dsf-pf-null-wwe&ts=1770814307427)

        <br>

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Meets surface mount constraint of project |                                                        |
    | H-Bridge let's both motors run simultaneously | |
    
2. DRV2603RUNR

   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/03f1cd0b-138a-411b-8144-3253873f775b" />

    * $0.56/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/DRV2603RUNR/3487230)
    * [Datasheet](https://www.ti.com/general/docs/suppproductinfo.tsp?distId=10&gotoUrl=http%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fdrv2603)

      <br>

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Meets surface mount constraint of project |                                                        |
    | H-Bridge let's both motors run simultaneously | |

3. MP6513LGJ-Z

   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/16af8c19-f7d3-4885-82ca-ab118397d909" />

    * $0.83/each
    * [link to product](https://www.digikey.com/en/products/detail/texas-instruments/DRV2603RUNR/3487230)
    * [Datasheet](https://www.ti.com/general/docs/suppproductinfo.tsp?distId=10&gotoUrl=http%253A%252F%252Fwww.ti.com%252Flit%252Fgpn%252Fdrv2603)



    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Meets surface mount constraint of project | Cannot run both motors simultaneously                 |
    

**Rationale:** A clock oscillator is easier ...


