# HeartSynch - An IoT Wearable Biometric sensor
## Designed by Aryan Ghosh, Chris Koehlmann, Joseph Carnide, and Simon Louis
Readme currently under construction!

HeartSynch is a portable and wearable biometric sensor and emergency device that allows a user's family to remotely monitor vitals and be contacted easily in the case of an emergency.

![Screenshot 2024-01-24 200620](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/99210d81-8186-4e51-ba9f-0b6cdac2338f)


https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/10078840-45ad-4ce8-8d1b-7f7a4a50caf8

![Screenshot 2024-01-24 200933](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/19ddc47e-7c95-4a41-aa0a-3c4ccdcb8304)


## Introduction
This project hit home for us and was inspired based on Simon's experiences living with his grandma. Simon's grandmother is 85 years old and is cared for by him, his parents and his siblings. Due to her age and medical conditions, someone always has to be home to take care of her, but even that does not ensure immediate response like last year when she fell in the bathroom, and neither he nor his family knew for an hour. This is what HealthSync aims to solve. A portable, easy-to-use device so that family members can be immediately alerted when their elderly family members get injured or have a medical emergency so that this never happens again.


## Table of Contents
- [Project Overview](#project-overview)
- [Hardware Setup](#hardware-Component)
- [Electrical Setup](#electrical-Component)
- [Software Setup](#software-Component)
- [Game Rules](#game-rules)
- [Early Work](#early-work)

## Project Overview
This project was created to solve a problem we see in the medical field today. All design and ideation are entirely original and created by the four contributing members of this repository. 

HeartSynch is a wearable device using an ESP32 development board to sense a user's heart rate, blood oxygen, temperature, and movement and displays all of these metrics on a website
![Screenshot 2024-01-24 200933](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/bb329d6b-4eb7-49f0-9e54-5475ddae5023)

## Hardware Component
The mechanical design of our system revolved around the constraints created by the electrical components we had to use. The chassis was built around the electronic components and went through multiple rounds of iteration to ensure all components were secure and the device was as comfortable as possible without sacrificing durability. All parts of the chassis are 3d printed using PLA and all files are included under the "mechanical" folder. The mechanical design features a ratcheting ladder strap that allows the user to wear and remove the device extremely easily while ensuring the device is secured.
![IMG_3688](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/bae5fa0f-2977-4ff0-9e95-fba89ce2aa39)

### Solidworks model
https://cdn.discordapp.com/attachments/1196842622187216936/1199801648428621914/image.png?ex=65c3dd5c&is=65b1685c&hm=b8279184a12381f1ad7836d9154a24343f555a8c3b13ac37f8c9f848190c7e02&
To ensure all parts fit together and that no time was wasted during construction. We thoroughly planned out the mechanical design using Solidworks. This also ensured that the device fit a wide range of users. 


## Electrical Component
The Electrical component boasts an ESP32 microcontroller development board mainly due to its built-in WiFi features. The ESP32 is powered by a 9V battery that is regulated into a 5V signal 
### Circuit Schematic to be implemented on the breadboard
![image](https://github.com/Aryan-G4/Dexerity-Dash/assets/119129454/d1be5c0d-4030-4d48-967f-dfd04706f4c5)

Using KiCad I created a schematic of the electrical system that had to be implemented to allow the FPGA to interact with the buttons and switches.

![486B255D-B9AB-4188-B3D1-C4E8ACC050CD](https://github.com/Aryan-G4/Dexerity-Dash/assets/119129454/e878659e-f6ae-4cb4-bc1c-b90ef3d461d8)
![7FF55709-1F49-4A41-8A71-BEF448E0833A](https://github.com/Aryan-G4/Dexerity-Dash/assets/119129454/18eb1549-8e2a-45c8-859b-1432bd40856f)
To ensure rapid production and prototyping, I used a breadboard to assemble the circuit show in the schematic, colour coding wires to allow for easy installation, debugging, and removal of wires. 

## Software Component

Using Quartus, VSCode and ModelSim, we wrote this game exclusively in Verilog. Our Final code is under _DEXTERITYDASH.V_, and all other files are drafts and tester code.

Shown below is a block diagram of how all different code modules and programs interact with each other. 
![Code Block Diagram](https://github.com/Aryan-G4/Dexerity-Dash/assets/119129454/0dcf2a52-2687-4f9e-aeea-b01f1b4b3609)

Despite our hardware and electrical components being quite complex given the scope of the project, we did not shy away from making our software just as complex, using several features of the DE1-SoC board.

Here is a list of Verilog features we implemented:
- A VGA output and Display showing a welcome screen as well as a max score and max time info screen.
- A Finite State Machine to control the two screens of the VGA
- Onboard FPGA Keys, LEDs, 7-Segment Displays, and GPIO pins
- A binary to decimal and a decimal to hexadecimal converter
- Multiple multi-bit wide registers to store data
- A timer implemented by generating a waveform and using clock crossing.
- Edge Triggered Flipflops to count score
- 

Here is a functional simulation of simulation of our game logic. GPIO_0 is the user input, and when it matches GPIO_1(the signal signifying which button we want to press), 'correctsignal' goes high for an instant and this causes the score counter to increase.
![modelsim](https://github.com/Aryan-G4/Dexerity-Dash/assets/119129454/5456b2c6-6864-46da-b954-85f8ec024fc1)


## Game Rules

We aimed to keep Dexterity Dash ~~TM~~ very simple as we want to test hand-eye coordination solely, eliminating external factors such as game complexity. To begin the game, the user simply presses the reset button, where they will be shown a timer and their score. The board should have buttons that light up and your job as the user is to press the lit up buttons, if the user presses a lit up button, then they score a point and a new button is lit up. The user must push their hand-eye coordination to score as many points as possible before the timer runs out. This allows them to have personal records to aim to beat, benchmarking their improvement. 


## Early Work










