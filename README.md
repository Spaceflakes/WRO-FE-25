# WRO-25

## Content
### **Folders**
* `t-photos` contains 2 photos of the team (an official one and one funny photo with all team members)
* `v-photos` contains 6 photos of the vehicle (from every side, from top and bottom)
* `video` contains the video.md file with the link to a video where driving demonstration exists
* `schemes` contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
* `src` contains code of control software for all components which were programmed to participate in the competition
* `models` is for the files for models used by 3D printers, laser cutting machines and CNC machines to produce the vehicle elements. If there is nothing to add to this location, the directory can be removed.
* `other` is for other files which can be used to understand how to prepare the vehicle for the competition. It may include documentation how to connect to a SBC/SBM and upload files there, datasets, hardware specifications, communication protocols descriptions etc. If there is nothing to add to this location, the directory can be removed.

### **Index**
 [The Powerpuff Trio](#The-Powerpuff-Trio) 
   
   - Members
   
   - Small introduction to them

   - Team Pictures
   
 [Hardware Materials](#Hardware-Materials)

 [Strategy](#Strategy)



## The Powerpuff Trio 
Members:
1) Vedant Varshney

11th Grader in Billabong High International School. First time participating in WRO but has participated many other robotic compenitions. Controlling the making of the github  and helping in other miscellaneous tasks

2) Siddesh Jain

11th Grader in Billabong High, second time in WRO, the lead engineer and the head of the developement team, responsible for the CAD and all the choices. Races FPV drones and likes math. Also is an idiot.
   
3) Sohaan Chhabra

A 12th grader at Billabong High International School. Returning WRO participant. Handles the logic, simulations, camera and LiDAR processing — basically speaks to AI more than humans. Also, races drones just to relax.


### Team Pictures

#### Formal

<img width="1600" height="1067" alt="image" src="https://github.com/user-attachments/assets/368da351-f256-4e32-9458-5950548c8b38" />

#### Informal

<img width="1600" height="1067" alt="image" src="https://github.com/user-attachments/assets/ba3a6192-5b88-4cce-b13b-81db39f576c6" />

<img width="1600" height="1067" alt="image" src="https://github.com/user-attachments/assets/d8d4433b-c129-4318-9237-dcf417b1724f" />


## Hardware Materials
- Rpi 4B/5

- LiDAR
  
- Servo

- Wheels

- Pi Cam

- Stepdown Module

- ToF

- ESC + Motor

- Battery

- Gears

- PCB

- CF

## Strategy

1) We are using a mix of LiDAR, Camera, and ToF (Time-of-Flight) sensors which enables obstacle avoidance.

- LiDAR offers highly accurate 3D mapping, critical for safe navigation and obstacle detection.

- ToF sensors enable fast, real-time depth measurement.

- Cameras provide detailed 2D imagery, that complements the 3D data from LiDAR and ToF.

By combining these technologies, we achieve a robust perception system that enhances accuracy, safety, and reliability in autonomous vehicle operation.


2) We are using ROS 2 as our main programming framework because it provides a modular and real-time system that connects all our sensors efficiently. This setup ensures smooth communication and coordination between the hardware and software, allowing our system to respond quickly and reliably. Additionally, ROS 2 makes it easy to expand and add new features as the project grows. Overall, ROS 2 gives us a flexible and robust platform suited for developing our project.
