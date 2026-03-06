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
    | Polybutylene Terephthalate for housing                            | Wired connection |
    |                                                                   |                     |

2. B2B-PH-K-S + battery
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/0c608c2b-a00e-46fa-8a63-660fc8f8542a" />

   <br>

   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/8b8dd72f-71a5-4f85-a9cb-f8a7e65900d0" />


    * $0.1 + $15.90 = $16.00
    * [Link to Connector](https://www.digikey.com/en/products/detail/jst-sales-america-inc/B2B-PH-K-S/926611)
    * [Datasheet](https://www.jst-mfg.com/product/pdf/eng/ePH.pdf)   
    * [Link to Battery](https://tinyurl.com/4jrj9ck6)


     | Pros                                                        | Cons                |
     | ----------------------------------------------------------- | ------------------- |
     | Allows for a wireless powering system | requires a bulky battery pack |
     | compact |  |

3. USB Type-C Receptacle
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/d363abe3-7112-42bb-bbe2-0b09c801fcc9" />


   * $0.78
   * [Link to product](https://tinyurl.com/mwn8w959)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Inexpensive                                                     | Requires CC resistors or PD controller configuration |
    | Compact                                                          | Wired connection |
    |                                                                   | More complex routing |


**Choice:** Option 2: B2B-PH-K-S + battery 

**Rationale:**
      This option was selected because it enables the system to operate using a battery-powered wireless power source, removing the need for a continuous wired power connection. A battery pack improves portability and flexibility, which is beneficial for mobile or embedded systems. Although the battery pack increases the physical size of the system, the advantage of independent operation and simplified power distribution outweighs the drawback of additional bulk. The connector also provides a secure electrical interface for delivering power to the rest of the circuit.


-----------

**Voltage Regulator (3.3V)**

1. TI TPS62840DLCR
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/8079f197-14c4-4a89-ad6d-ac629198c0c7" />



   * $2.08
   * [Link to product](https://www.digikey.com/en/products/detail/microchip-technology/MCP1640B-I-MC/2258562)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    |  Lower heat generation compared to basic buck regulators | Higher cost |
    | surface mount                            | Increased PCB complexity |
    | Inexpensive                                                 |                     |


2. MCP1640B Boost + LDO Combination (PMIC-style approach)
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/2168cf4c-ec8e-4b30-80e9-49f8b7691f25" />




   * $0.81
   * [Link to product](https://www.digikey.com/en/products/detail/microchip-technology/MCP1640B-I-MC/2258562)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Flexible voltage configuration                                   | Larger PCB footprint |
    | surface mount                            |                     |
    | Inexpensive                                                 |                     |


3. AP63203WU-7
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/d2e583f1-2c1e-49d2-84d6-fad8ae98f3c9" />





   * $0.71
   * [Link to product](https://www.digikey.com/en/products/detail/diodes-incorporated/AP63203WU-7/9858426?gclsrc=aw.ds&gad_source=1&gad_campaignid=120565755&gbraid=0AAAAADrbLljItgRzsVnNO3-5qPvu9sOfC&gclid=Cj0KCQiAy6vMBhDCARIsAK8rOgn7K4gVE3J7ADv3_Q5YxXXt60sMg7ncnEewleIUWCqzGQ6boCWI1fQaAiB6EALw_wcB)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Inexpensive | Moderate efficiency under higher load |
    | surface mount                            |                     |

**Choice:** Option 3: AP63203WU-7

**Rationale:** The AP63203WU-7 switching regulator was selected because it provides an efficient and compact method for stepping down voltage to 3.3V, which is required for many digital components. Compared to traditional linear regulators, this device offers better efficiency and reduced heat generation, particularly under moderate load conditions. Its surface-mount design reduces board space, helping keep the PCB compact. While efficiency decreases at higher loads, the regulator still provides a cost-effective and reliable solution for powering low-voltage electronics in the module.

**Voltage Regulator (6V)**

1. L7806ABD2T-TR
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/5440bc12-b84d-45bc-b3d2-7c09c83263a5" />




   * $0.96
   * [Link to product](https://www.digikey.com/en/products/detail/stmicroelectronics/L7806ABD2T-TR/585696)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | Light weight                                                     |  |
    | surface mount                            |                     |
    | Inexpensive                                                 |                     |
    | Eliminates the need for a secondary battery for motors |  |


2. R1173H001B-T1-FE
   
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/fd5982f8-6622-49c0-b57e-c7fda4734e8e" />



   * $1.06
   * [Link to product](https://www.digikey.com/en/products/detail/nisshinbo-micro-devices-inc/R1173H001B-T1-FE/10244877)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | surface mount                                              | Low current output |
    | Inexpensive                                                 | Low maximum input voltage |

3. NJM2887DL3-TE1
   
   <img width="438" height="247" alt="image" src="https://github.com/user-attachments/assets/82df19c4-4e3a-4048-9fe0-111b9cfc301e" />



   * $0.5
   * [Link to product](https://tinyurl.com/39h2whdx)
  
    | Pros                                                              | Cons                |
    | ----------------------------------------------------------------- | ------------------- |
    | surface mount                            | Low current output |
    | Inexpensive                                                 | Only available in bulk orders |



**Choice:** Option 1: L7806ABD2T-TR 

**Rationale:** The L7806AB2T-TR linear voltage regulator was selected to provide a stable 6V supply rail for components that require a higher operating voltage, such as motors. This regulator is lightweight, inexpensive, and available in a surface-mount package, making it easy to integrate into the PCB design. It also eliminates the need for a separate motor battery by converting the input supply to a regulated 6V output. Although linear regulators are less efficient than switching regulators, the simplicity, reliability, and low cost make this component a practical choice for the system's motor power requirements.

### Actuator

**Motor Driver**

1. TC78H670FTG,EL 

    <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/f63e0997-3339-4b0f-9176-77ec0daef7d2" />


    * $1.29/each
    * [link to product](https://www.digikey.com/en/products/detail/toshiba-semiconductor-and-storage/TC78H670FTG-EL/11568779)
    * [Datasheet](https://toshiba.semicon-storage.com/info/TC78H670FTG_datasheet_en_20240529.pdf?did=68606&prodName=TC78H670FTG)

        <br>

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Meets surface mount constraint of project |                                                        |
    | 4 H-Bridges let both motors run simultaneously | |
    
2. TB6612FNG,C,8,EL

   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/6f7ffedf-4cca-4a51-afae-f16fcfa72926" />

    * $1.82/each
    * [link to product](https://www.digikey.com/en/products/detail/toshiba-semiconductor-and-storage/tb6612fng-c-8-el/1730070)
    * [Datasheet](https://toshiba.semicon-storage.com/info/TB6612FNG_datasheet_en_20141001.pdf?did=10660&prodName=TB6612FNG)

      <br>

    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Meets surface mount constraint of project |                                                        |
    

3. TC78H620FNG,EL

   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/49882959-2c78-4c99-8b9a-53767750feca" />

    * $1.37/each
    * [link to product](https://www.digikey.com/en/products/detail/toshiba-semiconductor-and-storage/TC78H620FNG-EL/7056845)
    * [Datasheet](https://toshiba.semicon-storage.com/info/TC78H620FNG_datasheet_en_20161125.pdf?did=35802&prodName=TC78H620FNG)



    | Pros                                      | Cons                                                             |
    | ----------------------------------------- | ---------------------------------------------------------------- |
    | Inexpensive                               | Requires external components and support circuitry for interface |
    | Meets surface mount constraint of project |                  |
    


**Choice:** Option 2: TB6612FNG
**Rationale:** The TB6612FNG motor driver was chosen because it provides dual H-bridge functionality, allowing the system to control two motors simultaneously with forward and reverse direction control. This capability simplifies the circuit by integrating multiple driver functions into a single IC. The component is also inexpensive and available in a surface-mount package, making it compatible with the project's PCB constraints. While the driver requires additional external components for interface support, its ability to efficiently control motors and handle bidirectional current makes it well-suited for actuator control within the module.


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

**Rationale:** The Pololu 2371 6V motor was selected because it offers the highest torque output among the evaluated options, improving system performance and reliability during mechanical operation. The motor is small, lightweight, and compact, allowing it to fit easily within the design constraints of the module. Additionally, it operates directly from the existing 6V power rail, eliminating the need for an additional voltage regulator and simplifying the power architecture of the system. These advantages make it the most effective choice for delivering reliable actuation while maintaining an efficient and simple circuit design.

-----------

**FINAL COMPONENT SELECTION**

 | Subsystem | component | 
 | voltage regulator (3.3V) | AP63203WU-7 |
 | voltage regulator (6V) | L7806ABD2T-TR  |
 | power supply | B2B-PH-K-S + Battery |
 | motor driver | TB6612FNG |
 | motor | 2371 6V motor (Pololu) |

**Estimated Total Core Component Cost:**

AP63203WU-7 (0.71) + L7806ABD2T-TR (0.96) + B2B-PH-K-S + Battery (16) + TB6612FNG (1.82) + 2371 6V motor (Pololu) (23.95) = $43.44

**Cost Discussion**

The selected components were chosen to balance cost, efficiency, and performance. Most of the components are inexpensive and widely available, ensuring that the total system cost remains low while maintaining reliable operation. The use of integrated components such as the TB6612FNG motor driver and AP63203 switching regulator reduces the number of external components required, which simplifies the PCB design and further lowers manufacturing costs. Although certain components, such as the Pololu motor, have a higher individual price, their improved performance and reliability justify the cost by enhancing the overall functionality of the system.
