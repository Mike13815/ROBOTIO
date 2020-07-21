# ROBOTIO

~~~~~~~Introduction~~~~~~~~~

The purpose of this project is to create an interface to FANUC's Educational Cart robots via MODBUS TCP as well as an open source HMI to accompany it. https://www.fanucamerica.com/education/robotics

It can be used for Robots, PLCs, digital logic lab trainers, and even be placed into home appliances to allow for remote control.

The hardware and code are designed for the R30iB controllers but can support any interface up to 24V (48 with one external chip).

V1 supports 8 inputs and 8 outputs with the robot, as well as 2 in and 2 out for external systems such as tools, sensors, and actuators.

~~~~~~~Workflow~~~~~~~~~~~

1. Prototype Modbus Adapter on Breadboard - Finished. Prototype functioned with ESP8266
2. Apply and test with existing HMI Software - Finished. 14 months using OpenHAB as a temporary HMI to test hardware.
3. Prototype PCB - In progress. First boards are designed, fabricated, and in the mail. 
4. Create prototype Case - In progress. Case is printed and will be adjusted to best fit the boards once they arrive.
5. Finalize PCB - Hit all best case requirements and as many secondary objectives as possible.
6. Apply and test with existing HMI Software
7. Prototype portable HMI (Modbus Master) - In progress. 3.5" Touch screen LCD paired with ESP32. 
8. Create finalized case for IO PCB. Mount permanently.
9. Prototype HMI PCB.
10. Create case for HMI. 


~~~~~~~Interface Specifications~~~~~~~

- 8x Optically Isolated Inputs with LED indicators. 

Description: Select your resistor value based on your input voltage. Maximum of 50mA is allowed. Use the following equations: 
Resistor Value = (Maximum Input Voltage - 3V) / 0.02A
Resistor Wattage  = (Maximum Input Voltage - 3V)*0.02A

- 8x Darlington outputs using KID65783AF-EL/P drivers.

Description: Darlington was chosen over relays to maintain speed and life expectancy, allowing use of digital IO as a parallel interface.

- 2x Optically Isolated External Inputs 

Description: 24V Maximum. Both Anode and Cathode are given to allow for active high and active low sensors. 

- 2x External Outputs as 10A Single pole, double throw 125V Relays

Description: Version 2 will have physical isolation, but Version 1 is only designed for driving external 12V relays without taxing the IO power line. 
Do not connect mains power to the relays.

- 0.91" OLED display

Description: This exists solely to provide connection information and instructions. As an AP, it provides SSID and password. As a client, it provides status.

- ESP32

Description: The uC acts as a Modbus TCP slave device. Web interface is used for configuration. 
Connect external output A to external input A, Normally Open, 12-24V before booting to enter configuration mode. V2 will include a pushbutton.

~~~~~~~License~~~~~~~~~~

This project falls under Attribution-NonCommercial 3.0 Unported (CC BY-NC 3.0)

Attribution — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.

NonCommercial — You may not use the material for commercial purposes.
