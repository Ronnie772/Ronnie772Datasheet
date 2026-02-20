---
title: Module's Selected Major Components
---

## Module's Selected Major Components


### Power Management

**Power Supply**

1. PJ-102AH
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/711629bb-e7f1-4532-80e1-d3b02cca3b3b" />



   * $0.76
   * [Link to product](https://www.digikey.com/en/products/detail/cui-devices/PJ-102AH/408448)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Inexpensive                                                     | Side load fragility |
    | Polybutylene Terephthalate for housing                            |                     |
    |                                                                   |                     |

1. B2B-PH-K-S
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/0c608c2b-a00e-46fa-8a63-660fc8f8542a" />



    * $0.1
    * [Link to product](https://www.digikey.com/en/products/detail/jst-sales-america-inc/B2B-PH-K-S/926611)
    * [Datasheet](https://www.jst-mfg.com/product/pdf/eng/ePH.pdf)
 
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Inexpensive                                                     | requires a bulky battery pack |
    | compact                                                      |                     |
    | Ideal for exploration devices not connected to a wall   |                     |

-----------

**Voltage Regulator**

**Battery**

### Actuator

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
    * [link to product]((https://www.digikey.com/en/products/detail/monolithic-power-systems-inc/mp6513lgj-z/7361426))
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

**Motors**

1. M1N10FB11G 5V motor

     <img width="200" height="200" alt="Screenshot 2025-10-21 220238" src="https://github.com/user-attachments/assets/f51a6bd4-771a-4e88-a692-95ec44e6323e" />


    * $3.19/each
    * [link to product]((https://www.digikey.com/en/products/detail/nmb-technologies-corporation/M1N10FB11G/2417078))

    | Pros                                      | Cons                           |
    | ----------------------------------------- | ------------------------------ |
    | Inexpensive                               | Low torque                     |
    | Perfectly matches 5V rail                 | Tendency to spike in amperage when turned on |
    | Lightweight                               | Requires a diffrent Voltage regulator |
    | Available for bulk order for replacements |                                |
   
2. SE15K1BTYJ 12V motor
   
    <img width="200" height="200" alt="Screenshot 2025-10-21 220755" src="https://github.com/user-attachments/assets/200d5539-51be-4632-ba1e-df6a95210c7f" />


    * $9.24/each
    * [Link to product](https://www.digikey.com/en/products/detail/nmb-technologies-corporation/SE15K1BTYJ/6021448)

    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Higher Torque                                                     | Higher Price        |
    | Small and compact                                                 | Requires a diffrent Voltage regulator |

3. 2371 6V motor (Pololu)

   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/0165aa5f-2a6e-4fd3-abc3-cc830815b42e" />

   * $23.95
   * [Link to product](https://www.digikey.com/en/products/detail/pololu/2371/10450018?s=N4IgTCBcDa4MwHYCMACADgewDbYK4oBMBjFAWwwBcMAnEAXQF8g)

    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Highest Torque                                                    | Higher Price        |
    | Small and compact                                                 | Low RPM             |
    | Doesn't require an additional power rail                          |                     |
    | Lightweight                                                       |                     |
    
**Choice:** Option 3: 2371 6V motor (Pololu)

**Rationale:** The 2371 6v motor by Pololu is perfect match for our 5v power rail and eliminates the need for an extra one, keeping the PCB design simple. It is lightweight and has the highest toque output, therefore saving cost and increasing productivity.

-----------

**FINAL COMPONENT SELECTION**

**Estimated Total Core Component Cost:**

**Cost Discussion**
