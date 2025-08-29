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

 - Name of parts

 - Links

 - Rate per part

 [Mobility Management](#Mobility-Management)
 
 - Gives an overview of our bots parts

  [Power Management and Sense Management](#Power-Management-and-Sense-Management)

  - Gives an overview about the power consumption of our bot and use of each sensor

[Schematic Diagram](#Schematic-Diagram)

 - Shows all connections between the parts

[Obstacle Management](#Obstacle-Management)

- Basic overview of our strategy

- Shows our logic for dectecing the pillars and parking logic

[Our Journal](#Our-Journal)

- Tells our jounery making the bot


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

| Name |	Link |	Rate per part (in Rs.) |
|------|------|------|
| Rpi 4B/5	| https://www.raspberrypi.com/products/raspberry-pi-5 | -	|	
| LiDAR	| https://robu.in/product/ydlidar-x4-pro-360-degree-ros-scanner-for-navigation-collision-avoidance-10m/#tab-specification	| 8159 |	
| Servo	| https://robu.in/product/surpass-hobby-25kg-s2500m-servo/	| 1500 |	
| Wheels |	https://robu.in/product/65mm-robot-smart-car-12-rim-wheel-blue/ |	167 |	
| Pi Cam	| https://robu.in/product/arducam-8mp-imx219-175-degree-ultra-wide-angle-raspberry-pi-camera-module-compatible-with-raspberry-pi-4-model-b-pi-3-3b-and-pi-zero-2w/ |	2090	|	
|Stepdown Module | https://robu.in/product/mini560-dc-5v-5a-step-down-stabilized-module/ | 94 |		
| ToF |	https://robu.in/product/unsoldered-purple-gy-530-vl53l0x-time-of-flight-tof-laser-ranging-sensor-module/ |	179 |	
| ESC + Motor |	https://www.hobbywingdirect.com/collections/quicrun-brushless-system/products/quicrun-wp-10bl120-sl-system-g2?variant=41474386854003 |	15000 |	
| Battery |	- |	1500 |		
| Gears | - |	2500 |		
| PCB | - |	2000 |		
| CF | - |	1500 |	

### PCB & PPCB

##### PPCB

![WhatsApp Image 2025-08-23 at 5 41 59 PM](https://github.com/user-attachments/assets/215e8902-755f-4a60-9461-2f7f1db96a29)

##### PCB

<img width="989" height="699" alt="Screenshot 2025-08-27 133211" src="https://github.com/user-attachments/assets/086d20ed-95be-46f5-9201-f14b0872d43a" />

<img width="985" height="695" alt="Screenshot 2025-08-27 133220" src="https://github.com/user-attachments/assets/7cb36e20-b967-49e6-99e0-3f11862e1bf2" />
							

## Mobility Management

Our self-driving vehicle utilizes a rear-wheel drive (RWD) configuration, where both rear wheels are powered by a single brushless DC motor via a unified drivetrain and a robust 6:1 gear reduction. The wheels are 65 mm in diameter, providing an optimal balance between ground clearance and acceleration. Steering is accomplished using a high-torque Surpass Hobby 25kg S2500M servo mechanically linked to the front wheels through a precision steering linkage, under PWM control from a Raspberry Pi single-board computer.

The chassis is built from a unified bottom plate, providing a lightweight yet rigid foundation that maintains dimensional stability under load. All components are secured via counter-sunk steel screws, ensuring minimal chassis flex and maximum durability in high-dynamic maneuvers.

Speed, torque, and power calculations:

With a 6:1 gear reduction from the motor to the driving wheels, and a wheel diameter of 65 mm, the theoretical speed and torque can be calculated as follows:

Assume maximum motor RPM (post-gear reduction): 3000 RPM (typical for RWD brushless at this voltage/gear)

Wheel circumference: 
C = π × D

= 3.1416 × 0.065m ≈ 0.204m

At 3000 RPM at the wheel:

Linear speed: 
V = RPM × C / 60

= 3000 × 0.204 / 60 ≈ 10.2m/s  (36.7 km/h theoretical, but likely to operate at much lower speed for control and safety)

Since the gear ratio is 6:1, torque at the wheel is multiplied by 6 relative to the motor's output. If the motor provides 0.3 Nm, at the wheels this becomes 

0.3 × 6 = 1.8Nm

This setup allows for both quick acceleration and sufficient torque to manage sharp turns and inclines, which is crucial for obstacle navigation and parallel parking accuracy.

The ESC (Hobbywing Quicrun WP-10BL120, G2) regulates current delivery (up to 60A) for smooth and responsive throttle input, while PWM control from the Pi enables fine-grained speed and direction regulation.

In summary, the chassis, drivetrain, and steering are holistically integrated to provide robust, agile, and precise mobility

## Power Management and Sense Management

The propulsion and actuation circuits (ESC, motor, servo) are supplied by one LiPo battery. The ESC has a peak draw of 60A (operating at ~50%, or 30A continuous, during typical run), consuming a maximum of 14.8V × 30A = 444 W. The servo draws 10W at peak, and the combined power budget for the actuation side is kept within the safe limits by the battery’s discharge rating.

The Raspberry Pi and sensitive sensors (including Lidar and IMU) are isolated on the second 4S LiPo, with a DC-DC converter regulating voltage to 5V/3A as required for stable logic and communication. The Pi and Lidar each typically consume 12.5W (2.5A @ 5V per spec), ensuring ample runtime and reliable operation under competition conditions.

Wire gauge and power distribution are selected to minimize resistive losses, and all high-current connections use gold-plated connectors and fuses for safety and performance.

Sensor Suite Includes:

Lidar (12.5W): Primary for localization, mapping, and pillar/tracking detection in the obstacle challenge.

Raspberry Pi Camera (CSI-2): Used for vision-based lane detection and traffic sign/pillar color classification.

IMU (connected to Pi): Fusioned with odometry for accurate heading and slip detection.

All sensor data are fused on the Pi SBC, providing robust perception for navigation algorithms.

The Pi implements PWM control for motor speed and servo position, interfacing via logic-level converters with both the ESC and servo. Data logging, sensor fusion, and vehicle state estimation are performed real-time for optimal trajectory planning and reliability in both open track and obstacle challenges.

Power consumption summary during operation:

| Component | Power (W) | Power Source |
|-------|-------|-------|
| ESC & Motor |	222	| 4S LiPo #1 |
| Servo | 10 | 4S LiPo #1 |
| Lidar | 12.5 | 4S LiPo #2 (DC-DC 5V) |
| Raspberry Pi | 12.5 | 4S LiPo #2 (DC-DC 5V) |
| Sensors (misc) | < 5 | 4S LiPo #2 (DC-DC 5V) |

## Schematic Diagram

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/3870a5be-418f-4b19-b648-b6a3c6fe71e6" />

## Obstacle Management

### Strategy

1) We are using a mix of LiDAR, Camera, and ToF (Time-of-Flight) sensors which enables obstacle avoidance.

- LiDAR offers highly accurate 3D mapping, critical for safe navigation and obstacle detection.

- Cameras provide detailed 2D imagery, that complements the 3D data from LiDAR and ToF.
  
2) We are using ROS 2 as our main programming framework because it provides a modular and real-time system that connects all our sensors efficiently. This setup ensures smooth communication and coordination between the hardware and software, allowing our system to respond quickly and reliably. Additionally, ROS 2 makes it easy to expand and add new features as the project grows. Overall, ROS 2 gives us a flexible and robust platform suited for developing our project.

By combining these technologies, we achieve a robust perception system that enhances accuracy, safety, and reliability in autonomous vehicle operation.

### Logic
Open Challenge (Round 1)
1) ROS 2 Node Initialization

   - All system modules and ROS 2 nodes (including motion, perception, and sensor fusion) are launched.

2) Start Switch Monitoring

   - The robot waits in an idle state until it receives the official start switch input.

3) Lane Navigation & Dynamic Obstacle Avoidance Loop

- The vehicle drives forward, continuously evaluating the distances to the side walls.

- If both sides readings > 2.8m, the bot turns gently toward the side with the higher clearance to maintain centrality and avoid collision.

- The LiDAR module operates in parallel, providing high-frequency wall distance measurements. These are used in a feedback loop for counter-steering—dynamically correcting to keep the chassis parallel to the lane boundaries and maximizing lap speed and safety.

4) Lap Counter & Completion Logic

- Each complete revolution of the track increments a lap counter.

- If laps > 3, the system initiates the Parallel Parking Sequence. Otherwise, the navigation loop repeats.

Obstacle Challenge (Round 2)
1) LiDAR-Based Mapping & Pillar Detection Initialization

- The LiDAR system bootstraps, performing environmental scans to map both static field features and dynamic obstacles (pillars).

2) Pillar Tracking & Color Classification

- Upon locating a pillar by proximity in the LiDAR map, the camera is triggered to capture and classify the pillar’s color by majority pixel average.

- If green, a navigation waypoint is generated to the left of the pillar; if red, to the right.

- Waypoints are fed to the main path-planner, which recalculates trajectories dynamically for precise lane-keeping and object avoidance.

3) Loop Logic for Laps

- The above mapping, classification, and navigation run continuously throughout the three laps, with the robot always tracking its section, progress, and upcoming pillar positions.

4) Autonomous Parallel Parking Sequence

- Parking Lot Detection: At lap completion, sensors (LiDAR/camera) search for the parking lot boundary markers as per field specs.

- Initial Alignment: The vehicle slows, aligning itself parallel to the field’s outer wall by continuously comparing left/right LiDAR readings and using IMU orientation checks (< 2cm and < 2° tolerance).

- Entry Positioning: Advance until the rear wheel crosses the intended parking zone entry (based on rotary encoder ticks or real-time field feature estimation).

- Reverse Maneuver, Step 1: Start reversing with maximum steering toward the parking bay (usually right).

- Reverse Maneuver, Step 2: Once halfway inside, immediately steer to full opposite lock (left), continuing the reverse arc.

- Final Alignment: Stop as soon as sensors (LiDAR/camera) confirm the entire robot is within boundaries and parallel to the wall (verify < 2cm tolerance). If needed, issue slight forward/backward correction maneuvers using PID feedback from the sensors.

- Completion: Power down drive motors and alert completion via buzzer/LED.

### Flow Charts

##### Open Round

<img width="900" height="1600" alt="Mermaid Chart - Create complex, visual diagrams with text  A smarter way of creating diagrams -2025-08-23-150618" src="https://github.com/user-attachments/assets/40dfb668-d20c-4430-ace6-9c0c80ec5ad4" />

##### Obstacle Round

<img width="3609" height="3840" alt="Mermaid Chart - Create complex, visual diagrams with text  A smarter way of creating diagrams -2025-08-23-152100" src="https://github.com/user-attachments/assets/ef1781b0-1170-413e-aaca-fdf4bd511597" />

## Our Journal

### June:

- This month, we focused on event preparations. We decided on our team name, drafted the initial design of our car, and began placing orders for the required parts.

##### The Original Sketch of our car.

![WhatsApp Image 2025-04-30 at 11 18 56 PM](https://github.com/user-attachments/assets/194f330b-f4c7-4df5-b937-193b043bb70f)

## July:

- This month, we initiated 3D printing for our parts and began receiving the components we had previously ordered. Construction of the car officially started during this period. In the later weeks of July, we also began the coding process.
  
##### The car by the end of the month

  ![IMG_0383](https://github.com/user-attachments/assets/f131f32d-e917-477f-ac7f-650c9e254328)


## August:

- By the beginning of August, we had completed both the construction and coding phases, and then started testing, during which we fine-tuned everything to ensure the car was ready for the event.

  (pic of the final desgin of the bot)

## Gantt Chart

  <img width="1237" height="614" alt="image" src="https://github.com/user-attachments/assets/7c81e83d-e47e-4f85-9fee-920e514ff764" />


  

