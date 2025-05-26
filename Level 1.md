## **1.1 Intro To Aerodynamics & Aircraft Structure**
### **Objective:**
- Study Bernoulli’s Principle, Newton’s Third Law in aviation, and aerodynamic forces.
- Understand lift, drag, thrust, weight, and stability. 
- Learn about primary and secondary control surfaces.
### **Learning:** 
1. **Difference between UAV & UAS:**
   - ***UAV (Unmanned Aerial Vehicle)*** refers to the flying object alone, like the drone.
   - ***UAS refer (Unmanned Aerial System)*** refers to the complete aerial system i.e., it includes the drone, payload, control system etc.
2. **Significance of Newton's 3rd Law in Aviation:**
   - ***Helicopters:*** When the main rotors of the helicopter rotates, the body of the helicopter should also be rotating in the opposite direction, because of Newton's 3rd Law, but this does not happen because the tail rotor applies force to the body of the helicopter which prevents it from rotating. In absence of the tail rotor the helicopter body would indeed rotate in the direction opposite to the rotating rotors.
     - *How to stabilize a helicopter without a tail rotor?*
       ans: The following are few methods to stabilize a helicopter without the tail rotor:
	       - *Use 2 main rotors:*
	       ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/img-a1251.jpg?raw=true)
	         The top most rotor rotates in one direction and the rotor below it rotates in the opposite direction. This causes the resulting torque to cancel each other out. As a result no torque is applied to the helicopter body.
	       - *Use NOTAR design:*
	       ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/NOTAR.jpg?raw=true)
	        A fan inside the helicopter (2) pushes air through the tail boom (3). Some of this air exits through small side slots (Coandă effect) to create a sideways force (8) that cancels out the spinning caused by the main rotor (Newton’s 3rd law). A separate mobile jet nozzle at the tail (5) helps control direction (yaw). This setup makes the helicopter safer (no exposed tail rotor), quieter, and more stable in hover. It is very hard to control such helicopters.
	        ***Note:***
	        The **Coandă effect** is the tendency of a fluid jet (like air or water) to stay attached to a nearby curved surface rather than flowing in a straight line. In simpler words: When air is blown along a curved surface (like a round tail boom), instead of going straight, it "sticks" to the curve and follows it. This changes the direction of the airflow and creates a pressure difference — which can generate lift or sideways force.

| **Feature**                  | **Tail Rotor**                            | **NOTAR (No Tail Rotor)**                            | **Coaxial Rotors**                                  | **Tandem Rotors**                                     |
| ---------------------------- | ----------------------------------------- | ---------------------------------------------------- | --------------------------------------------------- | ----------------------------------------------------- |
| *Torque Cancellation Method* | External tail rotor (spinning propeller)  | Internal fan with Coandă effect (air blown sideways) | Opposite-spinning coaxial rotors cancel torque      | Opposite-spinning longitudinal rotors cancel torque   |
| *Safety*                     | Moderate – risk of tail rotor strike      | High – no exposed tail rotor                         | High – no exposed tail rotor                        | High – no exposed tail rotor                          |
| *Mechanical Complexity*      | Low to moderate – simpler gearbox         | High – ducted fan, air channels, Coandă slot control | Very high – complex dual rotor hub, synchronization | Very high – long drivetrain, synchronization          |
| *Maintenance Demand*         | Low – tail rotors are common & accessible | High – sensitive airflow systems                     | High – intricate systems and parts                  | High – large and complex drivetrain                   |
| *Lift/Thrust Capacity*       | Moderate – single rotor + tail rotor      | Moderate – no extra lift from anti-torque system     | High – both rotors contribute to lift               | Very High – large lifting area, ideal for heavy cargo |
| *Payload Capability*         | Limited by single rotor capacity          | Moderate                                             | High                                                | Very high                                             |
| *Weight Penalty*             | Lightest overall anti-torque system       | Added weight from internal fan and ducts             | Heavy – double rotor hub and blades                 | Heavy – longer fuselage and gearboxes                 |
| *Noise Level*                | High – tail rotor generates whine         | Low – very quiet (ideal for urban/police use)        | High – due to two large rotors interacting          | High – due to large rotor size                        |
| *Size and Shape*             | Moderate length and height                | Shorter tail (more compact)                          | Short but taller (vertical stacking)                | Very long (e.g., CH-47 Chinook)                       |
| *Power Efficiency*           | ~10–15% engine power goes to tail rotor   | Small portion goes to fan; more efficient than tail  | More efficient – no power wasted on tail rotor      | Very efficient – all power used for lift              |
| *Role/Mission Fit*           | General civilian & light military use     | Special roles: police, medevac, VIP transport        | Drones, compact helicopters, naval/military ops     | Heavy-lift transport, cargo (e.g., Chinook)           |
| *Parts Availability/Support* | Very high – widely supported              | Low – fewer models, less common                      | Moderate – fewer but increasing (e.g., drones)      | Limited – mainly military                             |
| *Example Helicopters*        | Bell 206, UH-1 Huey                       | MD 520N, MD 902 Explorer                             | Kamov Ka-52, Sikorsky X2, some drones               | Boeing CH-47 Chinook, CH-46 Sea Knight                |
- **Summary:**
  -  Tail Rotor: Simpler, lighter, widely used, but less efficient and noisier.
  - NOTAR: Safe and quiet, good for urban and civilian use, but more complex and costly.
  - Coaxial: High thrust in compact form, efficient but complex; ideal for drones and fast helicopters.
  - Tandem: Ultimate heavy-lifter; efficient and powerful, but very large and complex.

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/WhatsApp%20Image%202025-05-25%20at%2013.57.07_4a55ae16.jpg?raw=true)

- ***Drones:*** The blades of the propeller generate lift by pushing the air downwards, and as a result of the Newton's 3rd law the drone moves upward. 
3. **Significance of Bernoulli's Equation in aviation:**
<iframe src="https://www.kaggle.com/embed/asshraysudhakar/aviation-task-3?cellIds=1&kernelSessionId=209063107" height="300" style="margin: 0 auto; width: 100%; max-width: 950px;" frameborder="0" scrolling="auto" title="Aviation Task 3"></iframe>

4. **Sensor Unit:**
   a. ***Inertial Measurement Unit (IMU):***
    It's a sensor system that measures the drone’s orientation, acceleration, and angular velocity. It helps the flight controller understand how the drone is moving and correct its position in real time. The 2 main sensors which fall under IMU are:
     - ***Accelerometers:*** Measures the linear acceleration (linear motion) and force exerted on the drone in X, Y, Z axes.
       - Accelerometers no not report current speed, they report only the acceleration in a direction.
     - ***Gyroscopes:*** Measure angular velocity (rotational motion) around X, Y, Z axes.
       - Gyroscopes do not report the current angle, they report only the rate at which the device turns.
         
         **Working of accelerometer & gyroscope:**
         ![](https://media.githubusercontent.com/media/Asshrayyyy/MARVEL-Aviation-/main/IMU%20working.gif)
       
   b. ***Barometer:*** As the altitude increases the atmospheric pressure decreases, so pressure sensors like barometers help us give information about the altitude of the drone.
5. **Free body diagram of an inclined drone**, 
   ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Free%20body%20dia.png?raw=true)
   Here, the weight of the drone is 1KG. Therefore, the minimum required thrust being 10 N, the external thrust given by the RC is also 10 N. Since, the drone is inclined at an angle of 45° wrt ground, the  vertical component would be 10 Sin 45 = 7 N & horizontal component being 10 Cos 45 = 7 N. Since the 7 N of vertical force isn't sufficient to counteract the 10 N of gravity acting on the drone, the drone won't fly. The minimum required thrust in this case would be 14 N only then the vertical component would get 10 N of force, which is the minimum required force for the drone to hover.
6. **The four Basic forces in aviation:**
   ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/4.1.png?raw=true)
   - ***Lift:*** It is a +ve upward force generated by the pressure difference between the top and bottom sides of the airfoil. On the top surface, the pressure is large & -ve. This therefore creates a suction force and contributes most to the lift.
   - ***Thrust:*** It is a +ve horizontal force generated by the engine when they push air backwards (Newton's 3rd Law).
   - ***Drag:*** It is a -ve horizontal force generated by the relative airflow, it is present whenever the aircraft is in motion, it slows down the aircraft.
   - ***Weight:*** It is a -ve vertical force created by gravity.
### **Major Learning:**
1. **Concept of Lift:** 
   The more air deflected down, the more is the lift generated
   ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Lift%20Eqns%20for%20Av.png?raw=true)The above equations shows the lift equation where, 
   - L = Lift 
   - CL= Coefficient of lift [Depends on Shape of airfoil, Camber & Angle of attack]
   - Rho= Air Density [Depends on Pressure, Temperature, Altitude & Humidity]
   - V= Velocity of the aircraft in air
   - S= Surface area of the wing/airfoil

  ***Note:***
  - Here in order to change the lift of a UAV, we can only vary the V & CL (change AOA & Camber for specialized foldable airfoils).
  - Lift of the aircraft increases with increase in the air density. As, if the density of air increases then more air particles are pushed down, leading to better lift. 
  -  Lift of the aircraft increases with increase in the aircraft airspeed. As, if the velocity increases then more air particles come in contact and are pushed down, leading to better lift. 
  -  Lift of the aircraft increases with increase in the surface area of the wing. As, if the surface area increases then more air particles come in contact and are pushed down, leading to better lift. 
2. **Primary Control Surfaces:**
   - ***Elevator:*** They are present in the tail of the aircraft, responsible for pitch of the aircraft. 
     ![](https://media.githubusercontent.com/media/Asshrayyyy/MARVEL-Aviation-/main/Elevator.gif)
   - ***Rudder:*** Even rudder is present in the tail of the aircraft, responsible for changing the Yaw of the aircraft. 
     ![](https://media.githubusercontent.com/media/Asshrayyyy/MARVEL-Aviation-/main/Rudder.gif)
   - ***Ailerons:*** They are present on the wings of the aircraft, responsible for changing the roll of the aircraft.  
     ![](https://media.githubusercontent.com/media/Asshrayyyy/MARVEL-Aviation-/main/Ailerons.gif)

3. **Secondary Control Surfaces:**
   The secondary control surfaces are responsible for modifying the lift & aerodynamics of the aircraft. Few of the secondary control surfaces are as follows;
   
   - ***Flaps:*** Similar to ailerons but are closer to the fuselage, they generate more lift by increasing the surface area and at the same time the speed reduces due to the increased drag force. Therefore, flaps are extended only during take off and landings. 
     ![](https://media.githubusercontent.com/media/Asshrayyyy/MARVEL-Aviation-/main/Flpas.gif)
   - ***Slats/Kruger Flaps:*** Flap like structures but present in the leading edge of the airfoil, used only in large commercial airplanes & fighter jets.
     ![](https://media.githubusercontent.com/media/Asshrayyyy/MARVEL-Aviation-/main/slats.gif)
   - ***Spoilers/Airbrakes:*** Used in gliders & commercial airplanes to reduce the lift and slow down the aircrafts. 
4. **Brief about Pitot tube & Radio Altimeter:** 

| ***Instrument***          | ***Measures***            | ***How It Works***                               | ***Used In***                         |
| ------------------- | ------------------- | ------------------------------------------ | ------------------------------- |
| **Pitot Tube**      | Airspeed            | Measures total and static pressure         | Aircraft, drones, F1, weather   |
| **Radio Altimeter** | Height above ground | Sends radio waves and measures return time | Low-altitude aircraft operation |

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/pitot%20tube%20vs%20radioalt.jpg?raw=true)

### **References:**
1. [Working of accelerometer & gyroscope](https://www.youtube.com/watch?v=KuekQ-m9xpw)
2. [Coaxial Rotors](https://www.youtube.com/shorts/wAeNeJLHVmY)
3. [NOTAR helicopter](https://www.youtube.com/watch?v=7_zLojDF__w)

---
## **1.2 Understanding and Designing an Air foil**

### **Objective:**
- Understand the fundamentals of an Aerofoil, terms associated with it, the nomenclature, concept of turbulence. 
- Use Fusion 360 to model an NACA 4412 air foil of 100 mm chord length & 160 mm air foil span, in Fusion 360 using DAT to Spline/Canvas tool. 
- Simulate lift and drag at 25 m/s wind speed to ensure at least 5N lift, use Autodesk CFD for simulation. (Compare with 2 materials, composite based air-foil & wood based air-foil), also state the Angle of Attack in your report.
### **Major Learning:** 
##### **Basic science behind flight:**
![](https://media.githubusercontent.com/media/Asshray-Sudhakar/Marvel-Aviation-Level-1-/main/1.gif)
Also, **Angle of attack ∝ Lift** *{up to a certain value of AOA}*
If the AOA increases above a certain threshold i.e. above the **Critical Angle of Attack** then the lift starts to decrease and **causes stall**. 
##### **Basic Definitions:**
![](https://media.githubusercontent.com/media/Asshray-Sudhakar/Marvel-Aviation-Level-1-/main/3.gif)

![](https://media.githubusercontent.com/media/Asshray-Sudhakar/Marvel-Aviation-Level-1-/main/2.gif)
- ***Airfoil*** - Any surface, such as a wing, that provides aerodynamic force when it interacts with a moving stream of air.
- ***Leading Edge*** - Front tip of the airfoil.
- ***Trailing Edge*** - End tip of the airflow.
- ***Cord Line*** - Imaginary straight line that connects the leading & trailing edge.
- ***Camber*** - Curvature of the airfoil, where the upper camber means the upper curvature & the lower camber means the lower curvature.
- ***Mean Camber*** - Curved line that is midway between the upper and the lower surface, it is the average of upper and lower camber.
- ***Relative Airflow*** - Airflow with respect to the wings, basically air which hits the nose of the aircraft & opposes the aircraft motion.
- ***Angle of Attack (AOA)*** - Angle between chord line and the relative airflow.
- ***Angle of Incidence (AOI)*** - Angle between chord line & horizontal axis (x-axis).
- ***Wing Span*** - Distance from wing tip to wing tip.
- ***Planform*** - Shape of the wing from above (top view).
- ***Stagnation Point***- Where fluid velocity is ZERO.
- ***Aspect Ratio*** - Wing Span : Wing Chord {Gliders have high aspect ratio (less drag high aerodynamic efficiency) & Fighter jets have low aspect ratio (better maneuverability at the cost of increased drag)}
##### **Types of Airfoil:**
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/5.png?raw=true)
1. **Symmetric Airfoil:** 
   - The upper & lower camber of the airfoil are symmetrical, here the chord line & the camber line coincide with each other.
   - Used in aerobic planes as they easily allow planes to fly upside down.
   - Here lift is created by lifting the nose of the aircraft to create an AOA. When the AOA is 0 even the lift generated is 0. Example: Bullet
    ![](https://media.githubusercontent.com/media/Asshray-Sudhakar/Marvel-Aviation-Level-1-/main/6.gif)
2. **Non Symmetric Airfoil (Cambered Airfoil):** 
   - The upper & lower camber of the airfoil are un-symmetrical.
   - Here the lift is generated even when the AOA=0.
   - The below is an application of a non symmetric airfoil where -ve lift is generated. 
     - If camber line above the chord line, lift generated is upwards.
     - If camber line below the chord line, lift generated is downwards.
    ![](https://media.githubusercontent.com/media/Asshray-Sudhakar/Marvel-Aviation-Level-1-/main/7.gif)
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/8.png?raw=true)
##### **Turbulence:** 
When air flows over a plane or object and can't stay smoothly attached, especially on the back side, it separates, forming a low-pressure, messy air region called a wake, where swirling air (vortices) causes turbulence.
##### **Airfoil Nomenclature:** 
The naming of an Airfoil is done with the help of ***National Advisory Committee for Aeronautics (NACA)*** nomenclature. Where there can be 4,5 or 6 digits,
*For 4 digits,* **NACA ABCD**
- 1st Digit (A) gives the maximum camber as %(A)xc
- 2nd Digit (B) gives the position of maximum camber from the leading edge as %(Bx10)xc
- 3rd & 4th Digit (C,D) gives the thickness of the airfoil as %(CD)xc
Where, 
 c is the Chord length of the airfoil.
Example: 
NACA 4312. *(Assume chord length(c) = 200mm)*
Maximum Camber= 4% of 200, i.e. 0.04x200= 8mm
Pos. of max camber= 30% of 200, i.e. 0.30x200=60mm
Thickness of airfoil= 12% of 200, i.e. 0.12x200=24mm
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Screenshot%202024-11-22%20110308.png?raw=true)

*For 5 digits,* **NACA ABCDE**
- 1st Digit (A) gives the coefficient of lift (CL) as {(A)x(3/2)}/10
- 2nd & 3rd digit (BC) gives the position of maximum camber from leading edge as M% of c, where M=(BC)x(1/2) 
- 4th & 5th Digit gives the thickness of the airfoil as %(DE)xc
-> c, is the Chord length of the airfoil.
Example: 
NACA 46015. *(Assume chord length(c) = 200mm)*
Coefficient of lift= {4x(3/2)}/10, i.e. 6/10 = 0.6
Pos. of max camber= 60x(1/2)=30, i.e. 30% of 200 from leading edge,  0.30x200=60mm
Thickness of airfoil= 15% of 200, i.e. 0.15x200=30m
##### **NACA 4412 CAD+CFD:**
Span= 162.5 mm
Chord Length= 100 mm
*Note: 
The below airfoil is made using carbon fiber material.*
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/11%20NACA%204412%20Airfoil%20v5.png?raw=true)
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/10%20NACA%204412%20Airfoil%20v5%202.png?raw=true)
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/12%20Screenshot%202024-11-22%20224147.png?raw=true)

Therefore,
@ 15° AOA, wind speed 25m/s, chord length 100 mm & airfoil span 162.5 mm
***Lift= 8.24 N***
***Drag= 2.45 N***
[Click here](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/NACA%204412.pdf) to view the simulation report generated by Autodesk CFD.
### **References:**
All the resource materials specified in the task, no other resources used.

---
## **1.3 Basic UAV Assembly & Components Familiarization**
### **Objective:**
- Identify and understand flight controllers (Pixhawk, APM), ESCs, motors, propellers, and battery management. 
-  Learn about LiPo, Li-ion, and NiMH batteries, their charge cycles, and safety. 
-  Learn about different types of UAVs (fixed-wing, multirotor, hybrid).
- List the components you would need to make a Quadcopter drone (make sure all the components are compatible with one another) with minimum thrust to weight ratio of 2:1. Make a detailed report on this, along with reasons why the specific component was chosen. Explicitly show proof about each component being compatible with each other. 
- Do & show the manual pen and paper calculation of the drone flight time, thrust to weight ratio by reading the datasheet of the components. 
- Use E-calc to verify your results.
### **Learnings:** 
1. **Flight Controller:**
   It can be thought as the brain of the drone, which is responsible for integrating & controlling multiple sensors, aviation systems. There are many sensors which are built inside the flight controller. The scaling technology used here is MEMS (Micro-Electro-Mechanical Systems) technology, here it combines electrical and mechanical parts on a micrometer scale.
   -  ***Noise Elimination:***
     - In FCs there can be noise/interference due to unwanted vibrations, this noise ultimately affects the accuracy of the readings shown by these sensors. To tackle this issue modern drones use, "Sensor Fusion Technique", combining the reading of multiple sensors which show the same type of readings, like combining IMU+GPS+Radar can increase the accuracy of the altitude readings of the drone.
   - ***Protocol used in Pixhawk Orange Cube+ Flight controller:***
     - **MAVLink [Micro Air Vehicle Link]**
       It's a **lightweight communication protocol** used to send and receive commands, telemetry, and sensor data. It acts as a link between:
       - Flight controller ↔ Ground control station (e.g., Mission Planner, QGroundControl)
       - Flight controller ↔ Companion computer (e.g., Raspberry Pi, Jetson)
       - Flight controller ↔ Telemetry module or modem
     - The Mavlink can use I²C, CAN, SPI (for specific sensors), USB (Mission Planner), UART (Tx-Rx, Telemetry, GPS etc). Majorly UART is the one which is used, the below image helps us understand how UART is used within another protocol i.e., MAVLink here:
       ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Screenshot%202025-05-14%20000917.png?raw=true)
     - **MAVLink + LORA:**
       - You use LoRa modules  to transmit MAVLink messages over long distances.
       - The flight controller sends MAVLink packets via UART, and the LoRa radio transmits those packets. But, for this we would need an *external UART-based LoRa modules*.
    
2. **What if the drone goes out of the RF range of the RC?**
   Modern drones make use of RTH automation with the help of GPS, tower based tracking technology to make the drone come back to home.  
3. **Motor  & it's nomenclature:**
   ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/WhatsApp%20Image%202024-12-17%20at%2019.53.32_bb466681.jpg?raw=true)
   In a BLDC motor, 
   N- No. of teeth/coil windings
   P- No. of magnets/Poles in the BLDC motor
   So, if a motor packaging tells 12N-14P; It has 12 teeth & 14 magnets as shown in the figure below. 
   ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/12n14p.jpg?raw=true)

   Thumb rule while selecting the motors should be that the net thrust generated by all the motors should be at least 2x the weight of the drone. 
   - For racing drones etc., the thrust to weight ratio is about 8:1 (net thrust generated by the motor is 8x the weight of the drone), for Payload drones it is around 4:1 & for Normal drones it is 2.5:1.

4. **Propeller Nomenclature:** 
```
Propeller Specs reading: 
There are 2 main factors in the propeller i.e. Diameter & Pitch. Diameter is the measure (in inches) of the propeller from one end to the other  & Pitch is the distance (in inches) travelled by the propeller  in one revolution. It's denoted by 4 digits,
***Note:***
Example: if the numbering on the prop is ABCD R, {ABCD are nos}
AB-> Prop's diameter is AB inches
CD-> Prop's pitch is C.D inches
R-> Clockwise prop
If it has R at the end its a clockwise prop, if there is nothing or L then anticlockwise propeller.
Example: 1045 indicates 10" diameter, 4.5" pitch and its anticlockwise.
```

###  **Major Learning:** 
The following would be the materials needed to assemble a drone;
1. **Chassis:**
    If cost is not a concerning factor then Carbon Fiber would be the best chassis as it has best strength-to-weight ratio with high endurance. But if cost is a major concern then plastic or fiberglass would be the best choice for making a chassis.
    
2.  **Electronic Speed Controller (ESC):**
    An electronic circuit connected to the motor of the drone and the FC, which: 
    - Controls the speed and direction of the motor.
    - Prevents the motor from excess flow of current.
    - Converts control signals (from the FC) into electrical pulses to run the motors.
      -  **ESC selection:**
       The selected ESC should have 20% more amp reading than the motor.
       *{Amp reading is the amount of current drawn by the motor at 100% throttle}*
    
3. . **Propeller:** 
   No. of blades ∝ Drag ∝ Overall power req. ∝ (1/Efficiency) 
   **{2 blade propellers are the most stable}**

| **Parameter** | **Threshold** | **RPM** | **Thrust** | **Use Case**                         |
| ------------- | ------------- | ------- | ---------- | ------------------------------------ |
| High Diameter | > 8 inches    | Low     | High       | Normal drones, heavy payload, stable |
| Low Diameter  | < 8 inches    | High    | Low        | High speed race drones               |
| High Pitch    | > 4.5 inches  | Low     | Medium     | Moving Forward (Pitch motion)        |
| Lower Pitch   | < 4.5 inches  | High    | High       | Stable Hovering                      |
- ***High Diameter:*** Moves more air because of greater surface area, providing greater lift but spins slower.
- ***Low Diameter:*** Spins faster, but produces less lift, because of less surface area.
- ***High Pitch:*** Designed for speed, with a focus on forward movement.
- ***Low Pitch:*** Best for hovering and stability, generating more lift at lower speeds.
  
  **To summarize:**
  - Low Diameter & High Pitch = Speed and Agility {Hard to control}
  - High Diameter & Low Pitch = Stability and Hovering {Easy to control}

4. **Motors:**
   - ***Understanding the fundamentals of KV:***
     - KV is the *maximum theoretical rotation speed of the motor (in RPM) @ No Load*, when 1 volt is applied to it.
     *or Generator Analogy* 
     - If you manually install a shaft @ one end of the motor and rotate it 1450 times per minute (i.e. @1450 RPM), it would give you a 1 volt output. Therefore, for a lower KV motor let's say 750 KV, you just need to rotate 750 times a minute to generate 1 volt output.  
   
     - ***Relation between Kt & Kv of 2 same motors {Torque constant and the velocity constant of a motor}:***
       Consider two motors of the same size, i.e., 2822 1450 KV and 2822 750 KV. We usually associate KV with the torque of the motor, meaning a lower KV corresponds to higher torque, and a higher KV corresponds to a smaller prop and vice versa. However, this logic doesn't hold when the dimensions of the motors are the same.
       
       If we use the above generator analogy to understand the concept of KV, the lower KV motor should have more copper windings. This is because more windings are needed to produce more output voltage at lower RPMs. These additional windings create a stronger magnetic field, which compensates for the lower RPMs.
       
       Now, with more copper windings, the length of the copper wire increases, which increases the resistance of the windings. This increased resistance limits the current flowing through the windings, which reduces the changing magnetic field and thus significantly lowers the torque. In comparison, the motor with a higher KV rating has fewer windings and lower resistance, allowing more current to flow through the windings and increasing the torque.
       Therefore, we can conclude that the torque of the motor can't be judged by the KV value alone when comparing two motors of the same size.
   - ***If KV is misleading, how to compare 2 motors with the same size or any 2 motors in general?***
     See the Km value, its the motor constant just like Kv & Kt. Higher the Km value better is the overall torque and velocity efficiency of the motor. 
   -  ***What should be the motor Kv rating for your prop?***
     This formula isn't a standard formula but gives a rough estimate about the Kv rating of the motor that should be used for each prop size. 
     -  <iframe src="https://www.kaggle.com/embed/asshraysudhakar/aviation-task-3?cellIds=2&kernelSessionId=237214042" height="300" style="margin: 0 auto; width: 100%; max-width: 950px;" frameborder="0" scrolling="auto" title="Aviation Task 3"></iframe>
    
    Propeller Coefficient values for different sizes/diameters of the props are as follows, 
    - For 5" Prop,  Pc~ 9600. *{This gives 2400 KV, assuming 4S battery}*
    - For 6" Prop, Pc~ 7600. *{This gives 1900 KV, assuming 4S battery}*
    - For 7" Prop, Pc~ 6400. *{This gives 1600 KV, assuming 4S battery}*
   - ***Rule of Thumb for selecting a motor w.r.t props:***
     Bigger the size of the prop, bigger should be the size of the motor too.
   - ***Shaft of the BLDC Motor:***
     The shaft of a BLDC motor is the rotating metal rod at the center of the motor. For an outrunner motor shaft is internally fixed to the spinning outer part therefore, we can't see it. The thicker the shaft the better it is, as it is more strong against damages. But a thick shaft increases the weight of the motor.
   - ***Motor Hub:***
     Part of the motor which protrudes outwards where we mount the propellers.
   - ***Changing the rotation direction of the motor:***
     In order to change the rotation direction of the motor, just swap any 2 wires connected to the ESC.
   - ***Understanding the volume of a motor and how it affects the performance:***
     - Bigger motors i.e., motors with large volume are better because more copper windings can be efficiently fit (with least empty spaces) inside it, generating more magnetic field and thus, more torque. 
       ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Notes_250502_185223.jpg?raw=true)
   - ***What motor to choose for different propeller sizes?***
     The below chart shows the minimum volume of the motor that should be used for different propeller sizes.

| **Propeller Diameter (Inches)** | **Minimum Volume of the motor Req. <br>[It's the min value, so you can always choose motors bigger than what's specified here]** |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| 5                               | 600 * pi mm^3                                                                                                                    |
| 6                               | 700 * pi mm^3                                                                                                                    |
| 7                               | 900 * pi mm^3                                                                                                                    |
   
   **Note:** 
   *If we use propellers larger than what is recommended for a particular motor, then the load on the motor increases which may result in more current draw and cause overheating of the motor.*
   
5.  **Battery:** 
   We use Li-Po batteries in drone because of their low weight & high discharge rate. 
   C Rating/Discharge rating is how quickly the current can be discharged from the battery, basically supplying burst shot of current which usually lasts for a very less time, they are useful when giving throttle, when the throttle is given the discharging rate should be as high as possible. 
   - ***Battery terms breakdown:***
     - *mAh:* 
       Tells us about the capacity about the battery, more the mAh, more is the capacity, but as the capacity of the battery increases the weight of the battery also increases.
     - ***C Rating:***
       Discharge rate of the battery, it gives us the measure of how quickly the battery discharges itself.
       - **Ex:** If a battery of 3000 mAh is rated at 30C, then 30 times the capacity of battery, is the amount of burst of current it can supply without damaging the battery/drone, i.e. in this case it is 30x3000 mA= 90 A
   - ***Battery selection:***
     - ***Lithium Polymer(LiPo) Vs Nickel Metal Hydride Battery (NiMH):***
       - In NiMH batteries, the capacity slowly reduces as we keep using them, but in LiPo batteries, even after discharging, the output voltage stays more constant.
       - LiPo batteries have higher charge density than NiMH batteries, i.e. for the same size, a LiPo battery might give 11V, while a NiMH battery might only give around 8V.
       - A 6-cell NiMH battery can be roughly equal to a 2-cell LiPo battery in performance.
       - LiPo batteries are much more expensive compared to NiMH batteries.
     - *General Knowledge:*
       - The selected battery should have high capacity and high C rating, with minimal weight.
       - The selected battery should be compatible with the ESC, if the ESC is rated at 3S and the battery used is > 3S, then it can cook the ESC.
      - *Technical Knowledge:*
        - First calculate the net current drawn by the each of the motor @ 100% throttle, then multiply it with the no. of motors used in the drone, this will give the total current drawn by the motor. 
          - **Ex:** The motor draws 24 A of current peak at 100% throttle for some XYZ propellers, so assuming its a quadcopter, the total current drawn would be 24 * 4=96 A. In order to avoid heating issues, we choose a battery with sufficient spare, which can supply about 105 A of current easily. Now we can select the batteries by two way, 
            - *First way- Trial & Error:*
              Here a battery pack is given to us, and we calculate the total current it can supply by multiplying the battery capacity and the C rating (As shown in the above example for C Rating). In this case since we need 96 A of current and the supply current of battery is just 90 A. Therefore, we cant use that battery. So, we should either increase the capacity of the battery (mAh) or the discharge rate (C Rating). But If weight is a concern (like in racing drones) then we can't increase the battery capacity (mAh) above a certain threshold, so the only option left is to increase the C Rating of the battery. But if weight is not a concern then you can increase the battery capacity also.
            - *Keeping the Battery Capacity constant (mAh):*
              For some standard battery capacity say, 1800 mAh, find the required C rating of the battery, using the below formula.
              Battery capacity * C Rating = Required Current
              -- Here, Battery capacity is the constant value we are talking about, and the required current is something we already know (90 A in this case). Therefore, the C rating can be easily found. 
              **Note:**
              The C Rating found here is the minimum value of the C Rating we should be using.
      - ***Battery Combination:***
        a. 
        ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/LipoSeries%20conf.png?raw=true)
        
        b.
        ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/LipoParallel%20Confi.png?raw=true)

5. **Flight time Calculation:**
   ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Flight%20time%20cal.png?raw=true)
#### Making of a drone:

| **Component Name**                                                 | **Datasheet**                                                                                                                                                                                         | **Spec**                                                                                    | **Weight** |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ---------- |
| ***Frame:***<br>Tarot TL65B01 Iron Man 650 Frame                   | [Datasheet](https://robu.in/product/tarot-tl65b01-iron-man-650-foldable-quad-copter-frame/#tab-specification)                                                                                         | -                                                                                           | 476 g      |
| ***Flight Controller:***<br>Orange Cube+ Pixhawk Flight Controller | [Data sheet](https://docs.px4.io/main/en/flight_controller/cubepilot_cube_orange.html)<br>                                                                                                            | -                                                                                           | 73 g       |
| ***Motor:***<br>T-Motor MN3110 470KV                               | [Data sheet](https://robokits.co.in/multirotor-spare-parts/tiger-motor-esc-and-propeller/t-motor-motor/mn-navigator/t-motor-navigator-mn3110-470kv?products_id=1649:96de2547f44254c97f5f4f1f402711c1) | -> Volume: 7548 mm^3<br>-> Battery rating: 3-6S<br>-> Configuration: 12N14P<br>             | 98 g * 4   |
| ***Propeller:***<br>Orange Carbon Fiber Propeller 1045             | [Data sheet](https://robu.in/product/orange-hd-propellers-114711x4-7-carbon-fiber-props-1cw1ccw-1pair-black/)<br>                                                                                     | 10" Dia & 4.5" Pitch                                                                        | 26 g * 4   |
| ***ESC:***<br>Ready to sky 40A 2-6S ESC                            | [Data sheet](https://robu.in/product/40a-2-6s-esc-3-5mm-banana-connector/)                                                                                                                            | -> Cont. Discharge: 40 A<br>-> Peak Discharge: 60 A <br>(10 sec)<br>-> Battery rating: 2-6S | 34 g * 4   |
| ***Battery:***<br>MiniStar Lipo 1800mAh 22.2V                      | [Datasheet](https://www.drkstore.in/cnhl-ministar-lipo-1800mah-22-2v-6s-120cmax-200c-lipo-battery-pack-with-xt60/)                                                                                    | -> 1800 mAh<br>-> 22.2v ; 6S1P<br>-> Cont. Discharge: 120 C<br>-> Peak Discharge: 200C      | 302 g      |

![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/1%20act%20calc.jpg?raw=true)
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/2act%20calc.jpg?raw=true)
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/3%20act%20calc.jpg?raw=true)
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/screencapture-ecalc-ch-xcoptercalc-php-2025-05-02-20_31_33.png?raw=true)
The above is the free version of E Calc, because of which I didn't have access to the exact motor & the battery I used, that's the reason for such high deviation between then manually calculated & the E Calc results. Manually calculated results are more accurate and reliable.
### **References:**
All the resource materials specified in the task, no other resources used.

---
## **1.4 Propeller Blade Design & Simulation**
### **Objective:**
- Understand the basics of propellers, with nomenclature.
- Know the need of clockwise & anticlockwise propellers.
- Study,  
  - The identification of clockwise & anticlockwise propellers.
  - What effects the efficiency of the propellers.  
  - Conversion from 2 Blade to 3 Blade propeller.
- Design clockwise and counterclockwise propeller blades to generate min 8N lift.
- Show the pitch angle, and the diameter of the propeller.
- Run a Computational Fluid Dynamics (CFD) simulation in Autodesk CFD ONLY.
- Get introduced to toroidal propeller, and write a short note about it in the Blog Post section.
### **Learnings:** 
1. **Propeller Nomenclature:** 
```
Propeller Specs reading: 
There are 2 main factors in the propeller i.e. Diameter & Pitch. Diameter is the measure (in inches) of the propeller from one end to the other  & Pitch is the distance (in inches) travelled by the propeller  in one revolution. It's denoted by 4 digits,
***Note:***
Example: if the numbering on the prop is ABCD R, {ABCD are nos}
AB-> Prop's diameter is AB inches
CD-> Prop's pitch is C.D inches
R-> Clockwise prop
If it has R at the end its a clockwise prop, if there is nothing or L then anticlockwise propeller.
Example: 1045 indicates 10" diameter, 4.5" pitch and its anticlockwise.
```

No. of blades ∝ Drag ∝ Overall power req. ∝ (1/Efficiency) 
**{1 blade propellers are the most stable, then 2 blades}**

| **Parameter** | ** Threshold** | **RPM** | **Thrust** | **Use Case**                         |
| ------------- | -------------- | ------- | ---------- | ------------------------------------ |
| High Diameter | > 8 inches     | Low     | High       | Normal drones, heavy payload, stable |
| Low Diameter  | < 8 inches     | High    | Low        | High speed race drones               |
| High Pitch    | > 4.5 inches   | Low     | Medium     | Moving Forward (Pitch motion)        |
| Lower Pitch   | < 4.5 inches   | High    | High       | Stable Hovering                      |
- ***High Diameter:*** Moves more air because of greater surface area, providing greater lift but spins slower.
- ***Low Diameter:*** Spins faster, but produces less lift, because of less surface area.
- ***High Pitch:*** Designed for speed, with a focus on forward movement.
- ***Low Pitch:*** Best for hovering and stability, generating more lift at lower speeds.
  
  **To summarize:**
  - Low Diameter & High Pitch = Speed and Agility {Hard to control}
  - High Diameter & Low Pitch = Stability and Hovering {Easy to control}

###  **Major Learning:** 
- **Thumb Rule in Propeller selection:**
  _If pitch increases, diameter needs to decrease (and vice versa)_
  Since we know that, 
  *Higher Pitch* = More thrust per revolution, but also more load on the motor.
  *Larger Diameter* = More air moved (better for lift), but again more load on the motor.
  If both pitch and diameter are large, the motor might overheat or stall due to excessive current draw.
  So, the rule ensures that performance remains efficient and the motors operate within their safe limits by balancing the load between pitch and diameter.
  **Ex:** If you're switching from a 5x4.5 prop (5" diameter, 4.5" pitch) to one with a 6" pitch, you should reduce the diameter also by 1", i.e it should become 3.5" to balance the load.
- **Multiblade Propellers:**
  They are used when high speed, thrust is needed, also 3 blade props have better handling @ higher RPMs (Response Time), they also have reduced vibrations which can give better video footages incase of FPV drones, but all of this comes with the cost of increased drag, increased turbulence, increased power consumption & reduced overall efficiency. A propeller should have least amount of drag generated by the leading edge of the propeller (*Therefore, we always prefer propellers  with thinner blades*), and least amount of vortex formation at the tip of the propeller (*So, 2 blade props are more preferred than 3 blade props as in 2 blade props the vortex is formed only at 2 ends whereas in 3 blade props its formed at 3 ends*), but as we increase the number of blades, these factors also increase. 
- **Need of a clockwise & an anti clockwise propeller:**
  - If we used only clockwise/anticlockwise propellers, then the drone would always rotate in the opposite direction to the direction of rotation of the propellers, this is due to the conservation of Angular Momentum / Newton's 3rd Law. Therefore, in order to cancel the net torque acting on the drone we use both clockwise and counter clockwise propellers in a drone.
- **Identification of CW & CCW props:**
  - *Method 1: By Nomenclature:*
    If it has R at the end of it's numbering then its a clockwise prop, if there is nothing or L then anticlockwise propeller.
    - **Ex:** 1045 R- Clockwise Propeller & 1045 L or 1045 - Counter Clockwise Propeller.
  - *Method 2: By Looking at the Sideways of the Propeller*
    Look at the sideways of the propeller and imagine the airflow, i.e., imagine in which direction the propeller should rotate in order to push the air downwards.
  - *Method 3: Blowing Air from Top:*
    Keep the propeller at some flat surface and blow air from the top of the propeller, if the propeller rotates in clock wise direction then it's a clockwise propeller, and if it rotates in counter clockwise direction then it's a counter clockwise propeller. 
- **Propeller conversions (2 Blades <---> 3 Blades):**
  If the datasheet mentions certain type of 2 Blade propeller, but if we don't have a 2 blade propeller or if we want to use a 3 blade propeller for say some XYZ reason, then we use the below formula to convert a 2 blade to its 3 blade equivalent propeller.
  *Note: Pitch is kept constant* 
  ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Prop%20Blade%20Conv_250503_232918.jpg?raw=true)
- **CAD of 2-Blade Propeller:**
  *Diameter of the propeller = 165 mm*
  ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/New%20prop%201.png?raw=true)![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/New%20prop%202%20.png?raw=true)![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/New%20prop%203.png?raw=true)
- **CFD of 2-Blade Propeller:**
  *The thrust I got is 8.85 N; with propeller rotating @12,000 RPM*
  ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/CFD%20NEW%201.png?raw=true)
  ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Movig%20Air.png?raw=true)
  *Here we can see that the air is rotating around the propeller.*
  ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/CFD%20terms.png?raw=true)
  These are the few terms which I got introduced to while solving the CFD in transient mode.
### **References:**
All the resource materials specified in the task, no other resources used.

---
## **1.5 Understand about ESC**
### **Objective:**
- Control the speed of the BLDC motor with the help of a ESC & an Arduino.
### **Learnings:** 
The motor we are using is a BLDC motor A2212/13T 1000 KV, i.e., 22 mm is the motor diameter, 12 mm is the rotor height, 13 is the number of wire turns, and it gives 1000 RPM/volt.

There are two types of BLDC motors, outrunner & in runner. Outrunner motors have high torque and In runner motors have high RPM.
###  **Major Learning:** 
when a potentiometer is connected to an analog pin of a microcontroller (like Arduino or ESP32), it acts as a variable voltage divider. The ADC (Analog-to-Digital Converter) reads this voltage and converts it into a digital value between 0 and 1023 (for a 10-bit ADC). Now, The ADC value (0–1023) can be mapped to a PWM signal. This PWM signal is sent to an ESC to control speed.

1. ***Arming of ESC & its importance:***
    When initially powering the motor, the signal value must be the equal to or lower than the minimum value of 1 millisecond. This is called arming of the ESC, and the motor makes a confirmation beeps so that we know that it’s properly armed. In case we have higher value when powering, which means we have a throttle up, the ESC won’t start the motor until we throttle down to the correct minimum value. This is very convenient in terms of safety, because the motor won’t start in case we have a throttle up when powering.

2. ***ESC Calibration:*** 
   Every ESC has its own high and low points, and they might slightly vary. For example, the low point might be 1.2 milliseconds and the high point might be 1.9 milliseconds. In such a case, our throttle won’t do anything until it reaches that low point value of 1.2 milliseconds. To solve this issue, we can calibrate the ESC or set the high and low points as we want.

```
1. **Start with the throttle at maximum (high point)**
   
    - Before powering the ESC, set the throttle (potentiometer or transmitter stick) to **maximum**
        
    - This tells the ESC: **“This is the new maximum throttle”**.
        
    - Now, power on the ESC.
        
    - You will hear **beeps from the motor**, confirming it detected the new high point.
        
2. **Set the throttle to minimum (low point)**
    
    - **Wait for about 2 seconds** after the beeps.
        
    - Move the throttle to **minimum** (where you want the motor to stop).
        
    - The ESC will register this as **the new low point**.
        
    - Another set of beeps will confirm calibration is complete.
        
3. **ESC is now calibrated!**
    
    - The motor will now start responding **immediately** within the new range.
```

#### **Circuit Diagram:**
![](https://howtomechatronics.com/wp-content/uploads/2019/02/Arduino-BLDC-Motor-Control-Circuit-Diagram-Schematic.png?ezimgfmt=ng:webp/ngcb2)

#### **Actual Diagram:**
<iframe width="315" height="560"
src="https://www.youtube.com/embed/qDTcFEXMKlM"
title="YouTube video player"
frameborder="0"
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
allowfullscreen></iframe>

### **References:**
All the resource materials specified in the task, no other resources used.

---
## **1.6 RF Communication in UAVs**
### **Objective:**
- Learn about radio frequencies used in UAVs (2.4GHz, 5.8GHz, Lora).
- Understand the various security implications in the different wireless protocols used in drones, along with the emerging threats and ways of mitigation.
- Understand the procedure which goes behind the binding of an ELRS receiver.
- Bind the 2.4 GHz RP1 Rx with the TX 16S MK-ll.
### **Learnings:** 
- A frequency band is  how wireless data is transmitted between devices. There are generally 2 types, 2.4 GHz & 5.8 GHz. 2.4 GHz band is used in devices like wireless telephone, microwave oven. As lot of the devices used this band, the signal becomes over crowded and therefore cause a lot of interference. This led to the introduction of the 5 GHz band. It is used by fewer devices and thus, the signal is not much crowded.
- ***Wireless Channel:***
  In wireless communication (like Wi-Fi), a channel is a specific range of frequencies within a frequency band used to send and receive data.
  **Analogy:**
  Think of a channel like a lane on a highway: multiple cars (data packets) can travel, but only if they stay in their own lane (channel) or else they'll crash into others (interference).
  - So, if there is interference in one channel, that can be reduced by changing the wireless channel.
  - 2.4 GHz has 11 channels, out of which only 3 are non-overlapping. {As shown below}
    ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/Screenshot%202025-05-07%20005801.png?raw=true)
  - 5 GHz band has 25 non-overlapping channels.

| **2.4 GHz**                                              | **5 GHz**                                                 |
| -------------------------------------------------------- | --------------------------------------------------------- |
| Speed is slower (under ideal condition upto 300 mbps)    | Speed is faster (under ideal condition upto 1300 mbps)    |
| Range is longer                                          | Range is shorter                                          |
| Prone to interference as many devices operate on 2.4 GHz | Less prone to interference as less device operate on 5GHz |
| Easily penetrates to solid objects                       | Harder to penetrate to solid objects                      |
| Has 3 non overlapping wireless channels                  | Has 25 non overlapping wireless channels                  |

### **Major Learnings:** 
- ***Drone Communication Components & Their Vulnerabilities:***

| **Component**              | **Function**                              | **Protocols Used**                               | **Vulnerabilities**                          |
| -------------------------- | ----------------------------------------- | ------------------------------------------------ | -------------------------------------------- |
| **Command & Control (C2)** | Sends control signals from pilot to drone | 2.4 GHz / 5.8 GHz Wi-Fi, FHSS, DSSS, LTE, SATCOM | Signal jamming, interception, spoofing       |
| **Telemetry Data**         | Reports flight data (position, altitude)  | MAVLink, DroneCAN, LoRa, DJI Lightbridge         | Data injection, telemetry hijacking          |
| **Video Transmission**     | Sends live camera feed                    | FPV (Analog/Digital), OcuSync, Wi-Fi, 5G LTE     | Feed interception, MITM attacks              |
| **Navigation & GPS**       | Enables location tracking & geofencing    | GPS, GLONASS, BeiDou, Galileo                    | GNSS spoofing, jamming, DoS attacks          |
| **Payload Data Link**      | Transfers data from onboard sensors       | 4G/5G LTE, SATCOM, proprietary links             | Data leaks, interception, weak/no encryption |
- The following are the definitions of the few terms used in the above table:
  - **Signal jamming –** Blocking the drone’s signals so it can’t talk to the controller.
  - **Interception** – Spying on the drone's data or video feed.  
  - **Spoofing (Faking the source, ~"I'm the real GPS, trust me.")** – Tricking the drone with fake signals (like fake GPS).    
  - **Data injection (Inserting fake data, ~"Here’s a fake altitude, believe it.")** – Sending fake data to the drone to confuse or control it.    
  - **Telemetry hijacking** – Taking over the drone’s flight data feed. 
  - **Feed interception** – Watching the drone’s live camera without permission.
  - **MITM (Man-in-the-Middle) attack** – Secretly sitting between the drone and controller to spy or change data.
  - **GNSS spoofing** – Sending fake GPS signals to mess with the drone's location.
  - **DoS (Denial of Service) attack** – Overloading the drone’s systems so it crashes or stops responding.
  - **Data leaks** – Sensitive data accidentally getting out.
  - **Weak/no encryption** – The drone’s messages aren’t locked, so anyone can read or mess with them.
  
- ***Key Wireless Protocols & Security Risks in UAVs:***
  - **2.4 GHz & 5.8 GHz RC Signals**
    ***Use:*** Common for manual drone control
    ***Risks:*** Easily jammed, intercepted, or hijacked
  - **Wi-Fi Drone Control (802.11 Standards)**
    ***Use:*** Consumer drones like DJI, Parrot
    ***Risks:*** MITM attacks, De-authentication (Wi-Fi jamming), Packet injection for control takeover
  - **MAVLink Protocol**
    ***Use:*** Telemetry for autonomous drones
    ***Risks:*** No encryption by default & vulnerable to spoofing/data injection
  - **4G/5G LTE & SATCOM**
    ***Use:*** Lets drones work over mobile networks or satellites, even from far away.
    ***Risk:*** Can be hacked through cloud servers or online control systems.
  
- ***Emerging Threats in Drone Communication Systems:***
  - **GNSS Spoofing & GPS Jamming:**
    - Attackers can transmit counterfeit GPS signals, tricking drones into miscalculating their location.
    - ***Impact:*** UAVs can be forced to change flight paths or even crash.
    - ***Countermeasure:*** Use GPS + other satellites (like GLONASS, Galileo) and backup systems like motion sensors (IMU) to stay on track if GPS fails.
  - **Signal Hijacking & Remote Takeover Attacks:**
    - Weak encryption allows attackers to inject false commands into drone control links.
    - ***Countermeasure:*** Strong encryption (e.g., AES-256) and authentication-based command inputs.
  - **Video Feed Interception (FPV Spoofing):**
    - Analog FPV systems can be hacked, letting attackers watch the video or send fake footage.
    - ***Countermeasure:*** End-to-end encrypted FPV transmission (e.g., OcuSync).

- ***Other Strategies for Securing Drone Communication Networks:***
  - **RF Spectrum Monitoring:**
    Continuously scans radio signals (300 MHz to 6 GHz) to detect drone controllers, telemetry, and video feeds in real time.
  - **Deep Packet Inspection (DPI) for Networked Drones:**
    Analyzes data traffic (e.g., on LTE networks) to spot unusual drone behavior and identify unauthorized devices.
  - **Smart Counter-Drone Technologies:**  
    Uses AI to detect strange signal patterns and combines data from radio, radar, and cameras for accurate drone identification.
  - **Encrypted Communication:**
    Hard to hack because the data is locked and only readable by the drone and controller.
  - **Frequency Hopping:** 
    Keeps switching signal channels, making it tough for attackers to jam or block communication.
    ***Note:** Frequency Hopping won't work for GNSS spoofing/GPS jamming as, GPS signals use fixed frequencies.*

- ***LoRa:***
  LoRaWAN stands for Long Range Wide Area Networks, it uses un-licensed frequency band for long range communication. It is a communication protocol — a set of rules that devices follow to send and receive data over LoRa (the wireless signal).
  Analogy:
  - **LoRa** = The road cars (data) travel on.
  - **LoRaWAN** = The traffic rules (protocol) that say how fast to go, when to send, who gets priority, and how to stay safe.

| **Term**                 | **Meaning**                                                                                  | **Who Can Use It?**                                 | **Encryption**                                        | **Complexity & Cost**             | **Example**            |
| ------------------------ | -------------------------------------------------------------------------------------------- | --------------------------------------------------- | ----------------------------------------------------- | --------------------------------- | ---------------------- |
| ***Licensed Network***   | Uses radio frequencies that are reserved and paid for by companies (like telecom operators). | Only licensed operators (like Jio, Verizon, Airtel) | Harder to Jam                                         | More expensive and complex to use | 4G/5G, SATCOM          |
| ***Unlicensed Network*** | Uses free, open-to-everyone frequencies regulated by governments.                            | Anyone (home users, hobbyists, etc.)                | More vulnerable to hacking, jamming, and interference | Easy and cheap to use             | Wi-Fi, Bluetooth, LoRa |
  - Range of LoRa is about ~ 4.8 km in cities & about ~ 16 km in rural area, in order to extend the range one can use LoRa range extenders which are called as LoRaX.
  - LoRa devices can be classified into 3 classes, Class A, Class B, Class C. The following are few of the differences among them, 

| **LoRaWAN Class** | **Battery Life** | **Listening Behavior**  | **Message Reception (Downlink)**                                       | **Examples**                               |
| ----------------- | ---------------- | ----------------------- | ---------------------------------------------------------------------- | ------------------------------------------ |
| ***Class A***     | Longest          | Sleeps most of the time | Only after it sends (Uplink first)                                     | Fire Alarm, Flood Detector                 |
| ***Class B***     | Average          | Listens periodically    | Even if no message was sent                                            | Temperature & Humidity Metering            |
| ***Class C***     | Lowest           | Listens continuously    | Minimum delay (latency least) in receiving/sending (Downlink & Uplink) | Traffic Monitoring, Real-Time Applications |
 - ***LoRa Architecture:***
   ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/LoRa-Network-Architecture.jpg?raw=true)
   - End nodes are IoT devices like gas monitors, vending machines, water meters, and smoke alarms. These devices communicate wirelessly with a gateway using LoRa, which operates over specific RF (radio frequency) bands. The frequency band used by LoRa varies by region; in India, it operates in the 865–867 MHz band. Once the gateway receives the data from the end nodes, it forwards it to the network server using Ethernet or 3G, and the communication protocol used here is TCP/IP. The network server processes and verifies the data, then sends it to the application server—again via TCP/IP—where the data is used for applications such as monitoring dashboards or alerts.

- ***ELRS vs Cross-fire vs 4 in 1:***

| *Feature / Parameter*     | **ELRS (ExpressLRS)**                                                                          | **Crossfire (TBS Crossfire)**                                                                                                                        | **4-in-1 Multi-Protocol Module**                                    |
| ------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| **Frequency Bands**       | 2.4 GHz / 900 MHz                                                                              | 868 MHz / 915 MHz                                                                                                                                    | 2.4 GHz                                                             |
| **Range**                 | long (up to 20+ km with 900 MHz)                                                               | Very long (up to 50+ km in ideal conditions)                                                                                                         | Moderate (1-3 km typical)                                           |
| **Latency**               | Ultra-low (as low as 250 µs)                                                                   | Low (approx. 4-15 ms)                                                                                                                                | Moderate to High                                                    |
| **Protocol Type**         | Open-source, high-performance                                                                  | Proprietary (*By TBS- Team BlackSheep*), high-performance                                                                                            | Multi-protocol (FrSky, FlySky, DSMX, etc.)                          |
| **Use Case**              | FPV racing, long-range, budget builds                                                          | Long-range, professional use                                                                                                                         | Versatility across multiple receiver brands                         |
| **Receiver Size**         | Ultra compact                                                                                  | Compact                                                                                                                                              | Varies (external compatibility required)                            |
| **Community Support**     | Very active, open-source community                                                             | Strong community, closed ecosystem                                                                                                                   | Moderate, varies per protocol                                       |
| **Cost (Tx + Rx)**        | Low                                                                                            | Moderate to High                                                                                                                                     | Moderate                                                            |
| **Ease of Binding**       | Web UI/Lua Script (can be tricky)                                                              | Easy with TBS Agent X                                                                                                                                | Fairly easy via radio interface                                     |
| **Telemetry Support**     | Yes (bidirectional)                                                                            | Yes (bidirectional)                                                                                                                                  | Yes (depends on protocol)                                           |
| **Compatibility**         | Requires ELRS receivers                                                                        | Requires Crossfire receivers                                                                                                                         | Compatible with many RX brands (FrSky, FlySky, etc.)                |
| **Power Output**          | Up to 1000 mW (module dependent)                                                               | Up to 2000 mW (TX module dependent)                                                                                                                  | Generally lower (up to 100 mW typically)                            |
| **Firmware Updates**      | Frequently updated (open-source)                                                               | Managed via TBS Agent X                                                                                                                              | Manufacturer-dependent                                              |
| **Typical Use in Drones** | FPV drones, racing, budget builds                                                              | Long-range FPV, professional builds                                                                                                                  | Toy drones, multi-brand support                                     |
| **Disadvantage**          | - Requires flashing firmware (Hard for beginners)<br><br>- Only Compatible with ELRS receivers | - Only Tx and Rx made by that specific company (e.g., TBS) can work together, i.e. Tx & Rx are proprietary. <br><br>- Not Open source & cost is high | - Range is very low<br><br>- Latency is higher than ELRS/Cross fire |

- ***Binding of the Radiomaster TX16S MK-II (Tx) & the RP 1 (Rx)*** 
  - **ELRS (Express Long Range System):**
    The communication protocol followed by the TX 16S MK-II module is ELRS protocol, communication protocol refers to the language with which both the Tx & Rx communicates with. Few advantages of the ELRS protocols are as follow:
    - Really good range 
    - Low latency
    - Affordable
    - Size of receivers are very small & portable
    - Regular updates (Open Source)
    - Cross compatible with each other, i.e., Tx & Rx need not be of the same brand. Just that both the Tx & Rx should be of the same frequency. Ex: 2.4 GHz -2.4 GHz *or*  5 GHz - 5 GHz.  
  - **ELRS Setup:**
    ELRS firmware version is of the format, **Major.Minor.Patch**. For the Tx & the Rx to communicate with each other the Major number of both the Tx & Rx must be the same, minor & patch number may or may not be same.
    - ***Lua Script:***
      Lua script acts as the settings/configuration menu directly accessible from the radio transmitter (like Radiomaster TX16S). It lets you adjust both basic and advanced parameters like change packet rate(e.g., 50Hz, 150Hz, 500Hz), Adjust RF power output (e.g., 25mW to 1000mW depending on module), Update device settings (like binding phrase, switch mode) etc. of your ELRS setup without needing to reflash or connect to a computer.
    - ***Packet Rates:***
      It refers to the frequency at which new signals are transmitted to the Rx from the Tx module. Higher packet rates equates to lower latency therefore higher packet rates are generally used in racing or acrobatic FPV drones as high packet rates give smoother and more real-time control but at the same time higher packet rates also leads to reduced range and link reliability.
    - ***Telemetry:***
      Telemetry refers to the data drone sends back to transmitter/ground station, so one can see important information in real-time on the ground station.
      - 1:64 Telemetry Ratio meaning: For every 64 control packets the transmitter sends to the drone (Tx → Rx), 1 telemetry packet is sent back from the drone to the transmitter (Rx → Tx).
     - ***Power:***
       More the transmission power, more would be the range of the Tx-Rx. Radio wave strength drops off with distance according to the inverse square law. That means, to double the range, you need to increase power by 4×, not just 2×. But higher power also leads to quicker battery discharge.
     - *Checking Firmware version:*
       Turn on the built-in Tx wifi, connect to the Tx wifi on mobile/laptop. The password of the wifi is "expresslrs". Once this is done open 10.0.0.1 on any web browser this opens the ELRS webpage. Here you can see the firmware version of the Tx. Repeat similar process after powering on the Rx to see the firmware version of the Rx module.
  - **Updating Tx Firmware:**
    - Download & open ELRS Configurator.
    - Select the latest release version.
    - Select the target device, first do for Tx.
    - Select ISM in the regulatory domain.
    - Set the flashing method as wifi, then download the lua script by clicking on Build. Upload the updated lua script into the Tx's SD Card by going into scripts --> tool --> upload the newly downloaded lua script here.
  - **Updating Rx Firmware:**
    - Repeat the first 4 steps as above. (In 3rd step enter Rx specs in the Device & Device Category)
    - Set the flashing method as wifi, then download the lua script by clicking on Build.
    - Enter the ELRS webpage via Rx wifi and go to the update section, upload the new firmware there. 
  - **ELRS Binding:**
    - ***Binding without a Binding Phrase:***
      Power up & disconnect the ELRS Rx quickly for 2 times and then 3rd time connect it to the constant 5 V supply. This makes the ELRS Rx enter the binding phase (Flashing Green Light), and bind with whichever ELRS Tx in range.
    - ***Binding with a Binding Phase:***
      Power on the Rx module with 5 V supply, you should see quick flashing LED (indicating the Rx wifi is enabled). Once this is done, connect to the Rx wifi and open 10.0.0.1 on any web browser, here you can set a certain binding phrase. Repeat the same procedure and open the ELRS webpage for the Tx and re-enter the same binding phrase which was entered for the Rx. Once this is done, since both the Tx & Rx have the same binding phrase, they'll be automatically bound to each other. 
### **References:**
All the resource materials specified in the task, no other resources used.

---
## **1.7 Basics of PID**
### **Objective:**
- Understand PID tuning for stability in UAVs.
- Learn how GPS hold and altitude hold work in flight controllers, and tabulate the differences between the two.
- Make a self-balancing car which balances itself on the principles of PID control.
### **Learnings:** 
PID refers to Proportional Integral Derivative, it's a type of control system. The below are the notes I have prepared based on the resource materials provided,

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/PP1.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/pp2.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/PP3.jpg?raw=true)

- **P (Proportional)** – _Handles the **present** error_
  - It produces an output that is proportional to the current error.
  - If the error is large, the correction is strong.

- **I (Integral)** – _Handles the **accumulated past** error_
  - It sums up all the past errors over time.
  - Helps eliminate steady-state error (the constant error that P alone can’t fix).

- **D (Derivative)** – _Handles the **rate of change** of error_
  - It predicts the future trend of the error based on how fast it's changing.
  - Dampens the system by reducing overshoot and oscillations.

- Therefore, generally in drones to have a balance, the gain values of P > I > D, Incase the drone overshoots even after having D component, the proportional component would get it back because of the -ve error thus caused. 

- **Interesting analogy about PID:**
  ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/PID%20GPT%20Analogy.png?raw=true)
### **Major Learnings:** 
- **Alt Hold VS GPS Hold (Loiter):**

| **Feature**       | **GPS Hold (Loiter Mode)**                                                  | **Altitude Hold (AltHold) Mode**                                            |
| ----------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| *Sticks Centered* | Stays in same place (horizontal + vertical) even if the wind pushes it.     | Stays at same height but can drift horizontally due to wind.                |
| *Altitude Hold*   | When sticks are centered, the drone maintains and holds the current height. | When sticks are centered, the drone maintains and holds the current height. |
| *GPS Required*    | Yes                                                                         | No                                                                          |
| *Main Use Case*   | Hands-off hover at one spot outdoors                                        | Manual flying at a fixed height                                             |
| *Wind Handling*   | Fights wind using GPS and accelerometers                                    | You must manually fight wind                                                |

### **References:**
All the resource materials specified in the task, no other resources used.

---
## **1.8 Different Flight modes in Mission Planner**
### **Objective:**
Be familiar with the following flight modes available in the Mission Planner software and understand their use cases, Stabilize, ACRO, Altitude Hold, Auto, Guided, Loiter, Return to Home (RTL), Circle, Land, Drift, PosHold, Guided_NoGPS, Smart RTL, Follow Mode.
### **Learnings:** 
1. ***Stabilize mode:***
   No GPS required. The pilot has full control over the pitch, roll, yaw & also the  throttle as there is no automatic altitude hold. It's accuracy depends on how well the level calibration of the drone was done pre-flight. No GPS related failsafe like RTH work here. 
2. ***ACRO:***
   For advanced users, racers only, again there is no requirement of GPS here. In this flight mode, say for example you push the left throttle upward by 30% making the drone pitch forward, the drone won't pitch back/come to initial position even if the throttle is bought back to 0%, it'll come back to it's initial position only if the throttle is pulled down by 30%.
3. ***Altitude Hold:***
   No GPS required. The drone automatically maintains its current altitude using the onboard barometer when the throttle stick is centered. The pilot still has full manual control over pitch, roll, and yaw, but altitude is managed automatically unless the throttle stick is moved up or down. Pushing the throttle up makes the drone ascend; pulling it down makes it descend. Once the throttle is centered again, the drone holds the new altitude. Accurate barometer calibration is important. Like Stabilize, no GPS-based failsafe like RTH work here.
4. ***Auto Mode:***
   GPS is required. The drone follows a predefined autonomous mission consisting of waypoints and commands uploaded via Mission Planner. The pilot has no manual control during flight unless the mode is changed. The drone can take off, navigate, loiter, land, or trigger payloads all on its own, based on the mission plan. Failsafe like Return to Launch (RTL) are active and rely on GPS. Ideal for surveying, mapping, and repeatable automated tasks.
   **Note:**
   In Auto mode, the pilot can use the yaw stick to override the autopilot's yaw control , but the roll and pitch are not directly controllable. The autopilot takes control of roll and pitch to follow the planned mission.
5. ***Guided Mode:***
   GPS & Telemetry is required. The drone responds to real-time commands from a Ground Control Station (e.g., Mission Planner). You can command it to fly to GPS coordinates, take off, land, or even follow a moving object (with scripting). Here, the use of a Tx is optional as the complete drone is controlled from the ground station via the telemetry.
6. ***Loiter:***
   In Altitude Hold (AltHold) mode, when you release the sticks (letting them return to the center), the drone will maintain its current altitude using the barometer, but it will continue drifting in the direction it was moving, as there's no automatic position hold. In contrast, in Loiter mode, when you release the sticks (when sticks come to the neutral position), the drone will stop moving horizontally and will hold its position and altitude using GPS and the barometer, basically "parking" mid-air, unlike AltHold where it can drift with wind.
7. ***Return to Home (RTL):***
   RTL (Return to Launch) mode is a GPS-based autonomous mode where the drone automatically flies back to its home position (where it was armed or a set location), climbs to a preset altitude if needed, and then lands. The pilot has no manual control during RTL unless the mode is changed. It's mainly triggered by failsafes (like low battery or RC signal loss) or manually via a switch.
8. ***Circle:***
   Circle mode makes the drone fly in a circular path around a fixed point, maintaining constant altitude, radius (`CIRCLE_RADIUS`), and speed (`CIRCLE_RATE`). GPS improves accuracy but isn’t strictly required. The drone’s nose always points toward the center, and the pilot can control yaw but not roll or pitch. This mode is useful for orbiting a point of interest or performing stable rotations for scanning or photography.
9. ***Land:***
   Land mode makes the drone descend vertically for a controlled landing, managing its descent in two stages: a faster initial drop followed by a slower final descent below 10 meters (using `LAND_SPEED`). GPS is not required; it uses the barometer for altitude sensing. The drone disarms automatically after landing if the throttle is at minimum, ensuring a safe and autonomous touchdown.
10. ***Drift:***
    Drift mode lets the user fly a multi-copter like a plane with automatic coordinated turns, GPS is mandatory here. The pilot controls yaw and pitch, while roll is managed by the autopilot. Throttle is manually controlled to adjust altitude. This mode is great for FPV flyers and videographers.
11. ***PosHold:***
    PosHold is similar to "parking" the drone in mid-air. PosHold mode relies on GPS to accurately maintain a fixed position in 3D space. In this mode, the drone automatically maintains its position, heading, and altitude, essentially hovering in place. You can control yaw (direction) and throttle (altitude), but the drone will stabilize itself in terms of pitch and roll. It’s ideal for situations where you want the drone to stay in a fixed position without manual input on its horizontal movements.
12. ***Guided_NoGPS:***
    Guided_NoGPS mode allows a drone to receive attitude commands (such as roll, pitch, and yaw) without relying on GPS. This mode is typically used by on-drone companion computers (Like Jetson Nano, Rasberry Pie etc.) to control the drone's orientation in environments where GPS signals are unavailable.
13. ***Smart RTL:***
    Smart Return to Launch (Smart RTL) mode enables the drone to return to its home position by retracing a safe path, avoiding obstacles (using sensors like LIDAR, sonar, or cameras, depending on the drone's configuration) encountered during the outbound flight (path taken by drone form home/launch to it's current position). This mode is particularly useful when flying in areas with potential obstacles between the drone and its home location.
14. ***Follow Mode:***
    Follow Mode allows the drone to follow another vehicle or object that is publishing its position, maintaining a specified offset. This mode is often used in scenarios where the drone needs to track and follow a moving target, such as a person or another vehicle.
### **References:**
All the resource materials specified in the task, no other resources used.

---
## **1.9 DGCA Regulations**

### **Objective:**
- Understand and follow the laws and regulations related to flying of drones in India. Specifically study about the, “Drone Rules 2021 by the Indian Govt”.
- Study BVLOS regulations and flight planning considerations.
- Make a detailed flowchart on both the above topics.
### **Learning:** 
###### ***The below are few of the rules & regulations set by the DGCA & MoCA under the  New Drone Rules 2021;***
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/DGCA%20Flowchart.png?raw=true)

###### ***The below are few of the rules & regulations set by the DGCA for BVLOS flights;***
![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/BVLOS%20Flowchart.png?raw=true)
### **References:**
All the resource materials specified in the task, no other resources used.

---
