# Motor Controller Spring 2021 Technical Report

by LauRobby

+ [Summary](#Summary)
  - [System Description](#system-description)
  - [Terminology](#terminology)
+ [Research and Requirements](#research-requirements)
  - [Background Research](#background-research)
  - [Design Requirements and Key Parameters](#design-requirements-and-key-parameters)
  - [Design Requirements Derived from Rules](#design-requirements-from-rules)
  - [System Design](#system-design)
  - [Potential Designs -S elected Design and Justification](#potential-designs)
+ [Detailed Design (Schematic & Layout)](#detailed-design)
  - [Design Overview](#design-overview)
  - [Component Selection](#component-selection)
  - [Mounting and Packaging](#mounting)
+ [Bill of Materials](#BOM)
+ [Manufacturing Plan](#manufacturing-plan)
+ [Assembly Plan](#assembly)
+ [Testing Plan](#testing-plan)
+ [Project Reflection and Current Status](#project-reflection-and-current-status)
+ [References](#references)

## Summary
### System Description <a name="system-description"></a>  
The motor controller manages the speed and direction of the motor by modifying the amount of the current flowing through the three coils of our brushless DC motor. The main objective is to make the motor run with high efficiency, which is achieved by maximizing the torque applied to the magnetic rotor.
### Terminology <a name="terminology"></a>
MC - motor controller  
BLDC - brushless DC motor  
FOC - field-oriented control  
FET - field effect transistor, treat as an electrical switch  
IC - integrated circuit, semiconductor circuit that performs some task  
Driver - integrated circuit that provides the necessary current to drive a motor  
uC or MCU - microcontroller  
PCB - printed circuit board  
VESC - VESC project is an open source BLDC motor controller project that includes a circuit board and a software GUI. The VESC software is designed to work with a wide variety of hardware, from very low power to very high power.  

## Research and Requirements <a name="research-requirements"></a>
### Background Research <a name="background-research"></a>
We spent a lot of time working on designing a motor controller (link to v4) from scratch. While the hardware seems close to functional, we found programming the dsPIC MCU to be very challenging. Robby will share more knowledge on that after taking ECE4760. Since the actual code for the more efficient algorithms are quite complex and difficult to write, we were trying to use Microchip released code, but the compatibility of this code with the hardware we were using is unclear. It was also unclear how much more efficient a completely custom MC would be in comparison to a widely-used open source design.  
  During JanFab, we successfully debugged MCv1.0 and got two functional boards. Through this process, we not only gained a more in depth understanding of the VESC design, but also discovered several areas of improvement on that board.


### Design Requirements and Key Parameters  <a name="design-requirements-and-key-parameters"></a> 
  We use a Koford Motor (model 129H42A), which is a 24V, 10 pole BLDC motor. This motor is supplied with 3 hall sensors. It has a max no load speed of 1040 rpm and peak power output of 390 W.  
  For our purposes, we have estimated a max current of 20A, meaning the MC must have output power of 480 W.


### Design Requirements Derived from Rules <a name="design-requirements-from-rules"></a>
The only rules relevant to this subsystem are found in Article 67 (a), stating that the MC must be purpose-built for the Shell Eco-Marathon (i.e. we cannot use a purchased/modified MC, or motor controller evaluation kit). All PCBs manufactured for the MC must have “SEM” printed on them. As for MC software, it must be developed or integrated for the Shell Eco-Marathon. In short, we must design and build our own motor controller.

### System Design <a name="system-design"></a>
  The motor controller can be broken into hardware and software components. The hardware component has 3 main stages. In the first stage, we have a microcontroller which generates the necessary PWM signals needed to spin the motor. It also processes feedback from the power stage and inputs from the hall sensors and throttle. Since the microcontroller can only generate output signals with current on the order of milliamps, we need a driver stage that amplifies the current so that it is large enough to drive a motor. Lastly, we have a power stage with 3 pairs of high/low-side FETs. The connections between the FETs in each pair are taken as the phase signals to the motor. Our software is in charge of using inputs to generate the proper PWM signals.  
<img width="505" alt="image" src="https://user-images.githubusercontent.com/54723335/118558920-44c76500-b735-11eb-918b-de37af87ce2a.png">

### Potential Designs - Selected Design and Justification <a name="potential-designs"></a>
As discussed earlier in the background research section, we debated between two different options:
##### MCv4.0 (custom MC)
We spent an entire semester on this option. We used a dsPIC30F2010 MCU, the DRV8302 driver, and TPW1R306PL,L1Q FETs. We originally pursued this option because Eric Tang&Kahn had a lot of trouble with programming Tim’s VESC-based board. We reasoned that creating a MC from scratch would allow us to better understand the design, which would make debugging less black box. We had designed and assembled a breakout board with our driver and FETs, which we connected to a dsPIC motherboard and motor. Since we had little knowledge of programming microchip MCUs, we found application note motor control code for the family of MCUs that our particular one was in. 
#### MCv1.1 (optimized MCv1.0)
Over JanFab, we were able to get Tim’s original board to properly detect the motor again and fixed another populated board (see more about debugging in the “MCv1.0 Debug” page). By doing so, we were able to familiarize ourselves with the GUI and gain confidence in our ability to debug the VESC design. The Eric’s MCv3.0 was a variation of Tim’s MCv1.0 board and with some optimizations. Our MCv1.1 took some of these optimizations and made some further ones. 

#### Chosen design: MCv1.1
We decided during JanFab to change gears from the MCv4.0 to the MCv1.1. We were having numerous issues with our design, which we believe may have been a combination of hardware and software related problems. Firstly, our layout was not ideal, with some pours/traces being far too small. We were testing our breakout board with a small 8V motor. The most frequent issue that we encountered was a driver fault (DRV8302 nFAULT pin low). A likely issue was that the code we were using on our motherboard was not compatible with our hardware. We tried different codes. Some were written specifically for a dsPIC development board, which used the same MCU that we had, but had different hardware for the driver, FETs, and current feedback. Other code that we used would be for a different MCU in the dsPIC30F family that we could modify to compile onto the dsPIC30F2010. Using code that was not written for our specific design was the likely culprit in its failure. Furthermore, each of these codes strictly used only one type of control algorithm. Making it hybrid would require some sort of code fusion. As we did not write any of it, this could be quite a messy step. Most importantly, we did not feel that a custom board (which would not even be that custom) would be able to perform better than one heavily based on VESC. Since we realized that debugging that design was not as impossible as we had originally thought, and the firmware had options of a variety of different control algorithms (including FOC), optimizing that design would be the most advantageous move for improving our vehicle’s performance.  

 
## Detailed Design <a name="detailed-design"></a>
### Design Overview <a name="design-overview"></a>
#### Hardware
We first copied Tim’s schematic. We then made significant changes to the powering of the board, as well as the FETs used on the board (see more details in the “Component Selection” section). In addition to these changes, we made a few other optimizations, removing components of the original design relating to features that were not used on MCv1.0:
* Motor temperature 
* ADC2
* UART
* Servo
* CAN  
<img width="700" alt="image" src="https://user-images.githubusercontent.com/54723335/118386155-50a31200-b5e3-11eb-895d-68a9f0dc7b66.png">
<img width="700" alt="image" src="https://user-images.githubusercontent.com/54723335/118385910-408a3300-b5e1-11eb-9465-79bcaebc0fd6.png">
<img width="700" alt="image" src="https://user-images.githubusercontent.com/54723335/118385935-716a6800-b5e1-11eb-89cf-21e5c87f984c.png">
<img width="700" alt="image" src="https://user-images.githubusercontent.com/54723335/118385945-834c0b00-b5e1-11eb-8ada-c7881688bb7a.png">  
<img width="700" alt="image" src="https://user-images.githubusercontent.com/54723335/118386083-bba01900-b5e2-11eb-8bc0-f15a3da428e5.png">

#### Software
There are 3 primary methods of BLDC motor control: trapezoidal, sinusoidal, and field oriented control. Trapezoidal is the easiest; it applies a high voltage to one phase, a low to another and floats the third phase. There are 6 possible states and it changes a state every 60 degrees.  Sinusoidal requires a continuous rotor angle estimate rather than knowing within 60° what the rotor angle is. It knows the specific angle by sensing the specific feedback current. You also use a rotor angle estimation in FOC. In FOC, first you transform the 3 measured phase currents into a 2D representation using the Clarke transform. Then, you transform these into a rotating coordinate frame with the Park transform using the rotor angle. Since we can not configure the Koford motor with sensorless or sensored mode, we can only use FOC. After we increase the ramp time, we are able to achieve a smooth spinning. We use the code from the VESC gui, firmware version 3.33.

### Component Selection <a name="component-selection"></a>
#### Power converter
On the old design, the motor control takes 24V and uses the wide range buck converter on the driver chip to convert it down to 5V. Then, it uses a linear regulator to convert 5V to 3.3V. Those conversions are inefficient. In our design, we use a custom-made 5V to 3.3V power converter that is installed directly into the PCB and get 5V directly from an external 24V to 5V converter designed and manufactured by our team. [2021 Plan](../../../powerconverters/designs/Power_Converters_20-21.md)
#### FET selection 
The current FETs are very robust, but inefficient. We selected new FETs based on [Logan’s matlab script](./RR_FETs) to improve efficiency. The script calculated both high side loss and low side loss for each FET in the specified operation range. Power dissipated considered includes: conduction loss through on-resistance of FET, overlap loss during switching transition, gate drive loss due to Cgs, output charge loss due to Cds, body diode conduction loss during deadtime, reverse recovery charge lost due to body diode, sum of power loss through all FETs. 
![fet2](https://user-images.githubusercontent.com/54723335/118385881-015be200-b5e1-11eb-9a59-3be96d7b4946.jpg)
![fet1](https://user-images.githubusercontent.com/54723335/118385883-015be200-b5e1-11eb-9b51-0309a24bc0fb.jpg)
After considering the balance between manufacturing difficulty and efficiency, we selected [NTTFS5C454NL](https://www.onsemi.com/pdf/datasheet/nttfs5c454nl-d.pdf). Whether this is a good selection is yet to be validated (see testing section).
### Mounting 
The four mounting holes have 150mil inner diameter and 300mil outer diameter. The board can be securely mounted on the bulkhead of the car with M3 plastic bolts and nuts.

## Bill of Materials <a name="BOM"></a>
Link to BOM in Google Drive: https://docs.google.com/spreadsheets/d/1u5ol2KfBTuhV5x4sA7_EKpztsSiB66-sVXfifXFje00/edit?usp=sharing
 
## Manufacturing Plan <a name="manufacturing-plan"></a>
Like soldering most PCBs, we soldered the two hardest components first, the driver and the MCU. We used the soldering technique in the soldering tutorial video (add extra solder and then remove it using a wick). When soldering the driver, it is extremely important to establish a good connection between the thermal pad and the GND pad or the driver will send out a Fault signal (LOW on the fault pin). Other components are soldered based on their physical heights. We used a combination of solder and solder paste and finished populating in a short period of time.  

## Assembly
There are seven headers on the board and all of them are secured headers. The 5V and 24V input are both 2x2 molex connectors and the output to the three phases to the motor is a 2x3 molex header. Molex headers will take up more space than amp connectors but they are extra secure and can handle high current. The motor wires are connected to a male Molex connector using banana headers. The 5V to 3.3V converter is plugged on using MF headers, and we designed it so that the orientation is unique. The last header is a micro usb header that needs to be soldered securely and careful.

## Testing Plan <a name="testing-plan"></a>
  We used an incremental testing plan. For assembly, we tested connections after each component was soldered. For each IC, we tested that each pin had a good connection to the pad. We tested the connection of the thermal pad to ground later on when powering the chip.   
  After testing the soldering, we powered the chip, and checked that the fault pin on the driver was not low. We then worked to upload the bootloader to the MCU. After doing so, we worked to upload the firmware. We verified that it was successful by connecting our board to the GUI, and updating the config from there.  
  We then worked on receiving a motor detection result. The motor seems to move a bit, but gets stuck. We are currently working to debug the issue, which may be because of a power surge and ill-rated FETs. When choosing our FETs, we did not account for ripple, which could push the voltage above 30V when we supply 24V. We plan to test our motor controller on a lower voltage motor. [EDIT: turns out we ordered the wrong FETs, we ordered NTTFS4985NFTAG instead of NTTFS5C454NL. We will try again with the correct FETs]


## Project Reflection and Current Status <a name="project-reflection-and-current-status"></a>
  The open source VESC is a fantastic starting point for a motor controller and leaves a lot of room for improvement. Modifying its design is a good project, as we are not overwhelmed with the daunting task of creating a MC from scratch. We know that the baseline design works, and are given some opportunities to make design choices in optimizing the design. Although we are not completely done with this project, we were able to learn a lot from it and are optimistic that we will be able to get it to work.   
  This project is a good reminder to be very careful! It is very easy to fry components or your computer, as it is high power.   
  We are hoping to use a Raspberry Pi to program it. During the summer, we will use an ubuntu image for 64-bit Raspberry Pi 4. If we can do so, we have a portable and low risk device that can program the MC. https://ubuntu.com/download/raspberry-pi
  
## References
https://vesc-project.com/


