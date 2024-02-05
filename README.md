# HeartSynch - An IoT Wearable Biometric sensor
## Designed by Aryan Ghosh, Chris Koehlmann, Joseph Carnide, and Simon Louis
Readme currently under construction!

HeartSynch is a portable and wearable biometric sensor and emergency device that allows a user's family to remotely monitor vitals and be contacted easily in the case of an emergency.

![Screenshot 2024-01-24 200620](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/99210d81-8186-4e51-ba9f-0b6cdac2338f)


https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/10078840-45ad-4ce8-8d1b-7f7a4a50caf8

![Screenshot 2024-01-24 200933](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/19ddc47e-7c95-4a41-aa0a-3c4ccdcb8304)


## Introduction
This project hit home for us and was inspired based on a teammate's experiences living with his grandma. His grandmother is 85 years old and is cared for by him, his parents and his siblings. Due to her age and medical conditions, someone always has to be home to take care of her, but even that does not ensure an immediate response like last year when she fell in the bathroom, and neither he nor his family knew for an hour. This is what HealthSync aims to solve. A portable, easy-to-use, cost-friendly device so that family members of all classes can be immediately alerted when their elderly family members get injured or have a medical emergency so that this never happens again.


## Table of Contents
- [Project Overview](#project-overview)
- [Electrical Setup](#electrical-Component)
- [Software Setup](#software-Component)
- [Hardware Setup](#hardware-Component)
- [Early Work](#early-work)

## Project Overview
This project was created to solve a problem we see in the medical field today. All designs and ideation are entirely original and created by the four contributing members of this repository. 

HeartSynch is a wearable device using an ESP32 development board to sense a user's heart rate, blood oxygen, temperature, and movement and displays all of these metrics on a website. This website, with the purchase of a domain, can be accessed by any member of the user's family, showing them important biometric data in real time and alerting them when the sensor detects a biometric that is in an unsafe range (ex., A constant heart rate of 60bpm). This device allows for a more convenient safety net for users with health risks. 
![Screenshot 2024-01-24 200933](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/bb329d6b-4eb7-49f0-9e54-5475ddae5023)

## Electrical Component
![IMG_3720](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/cd76d473-1fb9-4cc8-be60-c57d2cdb5e28)

The Electrical component boasts an ESP32 microcontroller development board mainly due to its built-in WiFi features. The ESP32 is powered by a 9V battery that is regulated into a 5V, 3.3V and GND signal. The ESP32 requires a 5V input to run and all sensors, GPIO pins, and I2C pins require 3.3V. The electrical system made use of the MPU-6050 6-axis accelerometer used for fall and injury protection. Additionally we used the MAX30102 sensor to detect readings in heart rate, blood oxygen concentration, and temperature: all important biometrics to monitor for someone in at a risk of general health. Both sensors used I2C, connecting to the same ports of the ESP32. 

### Circuit Schematic to be implemented on the breadboard
![electrical schematic](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/355a4c2b-8783-4975-bae4-c4065def7e02)

Using KiCad, I created a schematic of the electrical system that had to be implemented to allow the ESP32 to pass all electrical rules checks and to properly recieve data from all sensors. 
To ensure rapid production and prototyping, I used a breadboard to assemble the circuit shown in the schematic and colour-coded wires to allow for easy installation, debugging, and removal of wires. 
![image](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/00b2a4d8-2e09-43c8-8ace-3f3381320d84)


## Hardware Component
The mechanical design of our system revolved around the constraints created by the electrical components we had to use. The chassis was built around the electronic components and went through multiple rounds of iteration to ensure all components were secure and the device was as comfortable as possible without sacrificing durability. All parts of the chassis are 3d printed using PLA and all files are included under the "mechanical" folder. The mechanical design features a ratcheting ladder strap that allows the user to wear and remove the device extremely easily while ensuring the device is secured.
![IMG_3688](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/bae5fa0f-2977-4ff0-9e95-fba89ce2aa39)

### Solidworks model
<img width="562" alt="image" src="https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/6ed4249d-8dfd-4c5e-9cc7-c51e4d49972d">
To ensure all parts fit together and that no time was wasted during construction. We thoroughly planned out the mechanical design using Solidworks. This also ensured that the device fit a wide range of users. 


## Software Component
![IMG_3698](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/3e7db2db-5fec-477b-af95-207d6d6d29c9)
![image](https://github.com/Aryan-G4/HeartSynch---IoT-Biometric-Sensor/assets/119129454/70630196-f0ef-4156-98cf-ad1564845c6d)

Using HTML, CSS, JavaScript, and C, our team was able to collect data from the sensors into the ESP32. We then used the ESP32 to host a local webpage to display and inform users of current biometric data. The webpage we created works on both PC and Mobile allowing for a seamless user experience. 










