## **2.2 Autonomous Flight Planning & Execution**
### **Objective:**
- Learn about the Heads Up Display (HUD) available in the Mission Planner.
- Using the built-in Ardupilot simulator (SITL), plan and execute a fully autonomous flight mission in Mission Planner.
- Implement waypoints, return-to-home (RTH), and failsafe settings. Configure a geofence around UVCE and test a small autonomous mission.
### **Learning:** 
- After opening the Mission Planner software, go to the second tab i.e., plan (flight planner) and on the right hand side set the home coordinates, since in this task we want a geofence around the college, we set the coordinates of the college i.e, 12.97530740069745, 77.5866144525168
- The **built-in simulator in Mission Planner**, also known as **SITL (Software In The Loop)**, allows one to simulate a drone running in ArduPilot firmware directly on the person's computer. It mimics real-world flight behavior, enabling user to test missions, tune parameters, and practice flying without needing physical hardware. 
- For setting up a simulation , go to the simulation tab and then click on the multi-rotor, download the stable file and connect the mavlink.
- Below is the Heads up Display of the Mission Planner;
   
     ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/mp_hud_detail.jpg?raw=true)
     
     1. **Airspeed (Groundspeed if no airspeed sensor is fitted)** – Shows how fast the aircraft is moving through the air; defaults to groundspeed if no airspeed sensor is present.
     2. **Crosstrack error and turn rate (T)** – Crosstrack error indicates how far the aircraft is from its intended path; turn rate shows how quickly it's changing direction.
     3. **Heading direction** – Displays the compass direction (in degrees) the aircraft's nose is pointing.
     4. **Bank angle** – Indicates how much the aircraft is rolled left or right (lateral tilt).
     5. **Telemetry connection link quality** – Shows the average percentage of successful data packets between the vehicle and ground station.
     6. **GPS time** – The current UTC time received from the GPS module.
     7. **Altitude (Blue bar is the rate of climb)** – Shows current altitude above sea level; the blue bar reflects vertical speed (positive for climb, negative for descent).
     8. **Airspeed** – Shows the aircraft's speed relative to the surrounding air.
     9. **Groundspeed** – Indicates how fast the aircraft is moving over the ground, it's the real speed of the UAV as it includes the affect of wind also.
    10. **Battery status** – Displays battery voltage, current, and remaining capacity percentage.
    11. **Artificial Horizon** – Visual representation of aircraft orientation relative to the Earth's horizon (pitch and roll).
    12. **Aircraft Attitude** – Shows pitch, roll, and yaw angles for understanding the aircraft’s orientation in 3D space.
    13. **GPS Status** – Displays satellite fix type (e.g., 3D Fix), number of satellites locked, and HDOP (Horizontal Dilution of Precision).
    14.  **Distance to Waypoint > Current Waypoint Number** – Shows how far the aircraft is from the current target waypoint and which waypoint number it is.
    15. **Current Flight Mode** – Indicates the active flight mode (e.g., Stabilize, Loiter, Auto), which controls how the aircraft behaves.
### **Major Learning:** 

##### ***Geofencing:***

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Geo%20Fenc.png?raw=true)

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/UVCE%20WP.jpg?raw=true)

1. **Gradient (Grad %):** 
   Gives the steepness of climb/descent of the UAV between the two waypoints in %.
      - +ve % --> Climb & -ve % --> Descent
        *Note:* |Grad %| values should be as low as possible as steep climb/descent is not good for the efficiency of the UAV, especially for planes but holds true even for drones.
2. **Takeoff & Landing:**
   ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Alt%20chngs.png?raw=true)
   
   It makes the drone rise X m above the ground and once this is done, it goes towards waypoint 1. To enable it,
   Right click on the screen and click on take-off. Set the takeoff altitude to 60m, 
   - If takeoff altitude too low then it can hit trees/buildings etc.
   - if takeoff altitude too high then grad % can increase, which reduces the efficiency and drains battery.
   - Takeoff does not have any latitudinal/longitudinal positions nor does it create a checkpoint on the map, this is because it is designed to takeoff from any given location once the flight mode is set to auto.
   - Move the takeoff checkpoint in the action panel to 1st position, i.e., to waypoint 1.
   
   Similarly set a LAND waypoint at the end. Now, set the altitude of each waypoint accordingly, so that the drones takes off to a certain altitude in steps of increasing altitude, then surveys the region, and then gradually decreases the altitude in order to land in a set waypoint.

3. **Prefetching:**
   Press & hold alt and select all the waypoints, right click and hit on prefetch. [Max Zoom=20]
   - Prefetch downloads the image of the map, and stores it locally. This helps us view where the drone moves over the map even in cases of no cellular connections (in remote areas). Without prefetch we can still see the drone icon, position, heading, altitude, but the background may appear black or grey as the map tiles weren't downloaded

##### **Surveying:**

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Survey.png?raw=true)
*Note:*
Here the top image shows the customization window of the survey (grid), and the bottom image shows the final waypoints.

1. Add a takeoff waypoint, ex: 60m.
2. A *grid needs to be created using Polygon WP ONLY*. So, 
   - Right click on the map
   - Draw polygon
   - Add polygon point {Make a boundary to survey using the polygon pinpoints}
   - Auto WP
   - Click on Survey (Grid)
   - Do necessary customizations.
   - Click Accept
3. Come out of polygon mode:
   - Right click on the map
   - Draw polygon
   - Clear polygon
4. Now just like before using normal waypoints define a proper path for landing and adjust the takeoff and landing altitudes.

*Note:*
- If the number of waypoints in a project is very high, and you want to insert a waypoint between any two waypoints, then right click on the map and click on insert waypoint. It would then ask for where the waypoint is to be inserted, i.e., after which waypoint.

##### **Uploading of Missions:**
On the right hand side of the flight planner interface, there are 5 ways to upload the waypoint missions, they are as follows:
-  ***Load File:***
	Loads a previously saved waypoint mission file (.waypoints) from your computer into Mission Planner application.
- ***Save File***
  Saves the current mission plan (all waypoints, commands, etc.) to a file in the user's laptop/computer for backup or later use.
- ***Read:***
  - Reads the current waypoints and mission commands from the drone into Mission Planner application.
  - Useful to check what's already loaded on the drone.
- ***Write:***
  - Sends the mission plan from Mission Planner to the drone at a standard (safe)
    communication rate.
  - Ensures mission is uploaded completely and correctly.
- ***Write Fast***
  - Sends the mission plan to the drone at a faster rate.
  - Can be quicker, but slightly riskier if the link is unstable — not recommended for poor telemetry links.
##### ***Video of Automated flight:***

<iframe width="560" height="315" src="https://www.youtube.com/embed/VJHa3IAiXwc?si=MYhkMvAEBcuYvzj8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### **References:**
Chat GPT for HUD of Mission Planner

---
## **2.3 Intro To MATLAB**
### **Objective:**
- Complete MATLAB Onramp & Simulink Onramp courses and upload the certificates.
### **Learning:** 
Below is the certificate of completion of my MATLAB Onramp course.
[Click here](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/On%20Ramp%20Study%20Material.pdf) to view the handbook for the course.
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/MATLAB%20OnRamp%20Certificate.png?raw=true)

Below is the certificate of completion of my Simulink Onramp course.
[Click here]() to view the handbook for the course.
IMAGE
### **References:**
All the resource materials specified in the task, no other resources used.

---
## **2.4 Advanced PID Tuning**
### **Objective:**
- Have a strong understanding about PID Controllers, with the help of the resource material given below.
- Connect the UAV to Mission Planner, observe & manipulate the default PID values.
- Make a self-balancing car which balances itself on the principles of PID control, adjust PID parameters one at a time.
### **Learning:** 
Pre-requisites learned from 7th task of Level 1.
### **Major Learning:** 
#### PID Controllers, it's problems:
The below are the notes I made referring the given resource materials:

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/4.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/5.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/6.jpg?raw=true)

#### Noise & Modelling in PID Controllers:
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/7.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/8.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/9.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/10.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/11.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/12.jpg?raw=true)
![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/13.jpg?raw=true)

#### PID Tuning in Mission Planner:
- ***Interfacing & Setup:***
  - **Set the flight mode:**
    - Setup --> Mandatory Hardware --> Flight Modes -->  Set Flight Mode 1 in the dropdown menu. [Recommended to start with stabilize mode]
  - **Start with the default values of PID:**
    - Config --> Extended Tuning
    and tune it as per the observations made in the test flight. 
- ***PID Tuning:***
  - **P Tuning:**
    Increase P if the drone feels sluggish/unresponsive. Also, if P is too high, the drone may oscillate rapidly around the target.
  - **I Tuning:**
    Increase I if the drone slowly drifts from the set point (Ex: doesn’t hold position over time). But if I is too high then it may cause sudden overshooting, iff the system was forcibly put to rest for a long time *(soln. is Anti wind up explained in the above handwritten notes)*, too high values of I can also cause slow oscillations that grow over time,
  - **D Tuning:**
    Increase D if the drone oscillates after a sharp change (sharp turn/altitude shift), also increase it if there are natural oscillations in the drone when in air, but too much D can cause increased noise in the control system *(Reason along with mathematical proof explained in the above handwritten notes)*. 

#### Self Balancing Car:
- **Practical Demonstration of PID using Self Balancing Car:**
  ![](https://github.com/Asshray-Sudhakar/Marvel-Aviation-Level-1-/blob/main/PID%20Manual%20Task.png?raw=true)
  The above is the circuit diagram of the self balancing car. The self-balancing robot implements a closed-loop control system using PID (Proportional-Integral-Derivative) to maintain its vertical orientation based on real-time pitch angle feedback from an MPU6050 IMU.
  
  **Actual Working of the Self Balancing Robot:**
  VIDEO

### **References:**
All the resource materials specified in the task, no other resources used.

---
## **2.5 Rules in the Rule Book Written by Blood:**
### **Objective:**
- Take an example of a previous Air Crash  from [Wyngx](https://www.youtube.com/@_WyngX/videos) or any other source of your choice. 
- Write a detailed report of the air crash investigation, the report should include:
    - Details of the flight, place, time, pilot details and an introductory paragraph about the accident which occurred /was about to occur including the losses occurred.
    - Explain in brief about the aircraft.
    - Using the Swiss Cheese Model analyze the key contributing factors (technical, human, environmental etc.) and also explain how each of these factors (layers of the Swiss Cheese) accelerated the accident when aligned together.
    - State the various theories and assumptions which took place during the investigation and also mention the reasons which led to the elimination/confirmation of these theories.
    - Reflect on what lessons were learned and how aviation standards changed post
      accident.
### **Report:** 
I reported on the Crash of Air India Express flight 1344, which crashed on the Kozhikode Int'l Airport on 7th of Aug 2020. 
[Click Here](https://github.com/Asshray-Sudhakar/Air-Crash-Investigation-Report/blob/main/Air%20India%20Express%20Flight%201344%20Crash%20Report.pdf) to view my Air Crash Investigation Report.
### **References:**
1. [Air Crash Investigation Source Video](https://www.youtube.com/watch?v=m_LAiLPN-EE)

---
## **2.6 Flight Data Logging & Analysis**
### **Objective:**
- Extract log files from a Pixhawk/APM flight controller.
- Analyze flight stability, GPS accuracy, battery performance using Mission Planner.
- Generate graphs for:
  - Altitude over time.
  - Throttle vs Battery consumption.
  - GPS drift analysis.
  - Suggest improvements based on data trends.
### **Learning:** 
There are two types of Logs:
1. ***Telemetry Log:***
   Recorded on the computer if you have a telemetry connected to the drone, it requires a real time connection to the computer during the flight.
2. ***Dataflash Log:***
   Recorded on the flight controller during the flight, some FCs record the data on the internal memory and some others need external SD Cards to be connected to the FC.
   
### **Major Learning:** 
1. ***Downloading of Dataflash Log from the FC:***
   - Just below the HUD there is options of Telemetry Logs & Dataflash logs, under each there are multiple options. 
   - We can download the Dataflash Log from the computer via a USB cable.
2. ***Auto-Analysis of log files:***
   Under the Dataflash analysis log section there is a option for auto analysis, click on that and upload the log file.
3. ***Review a log:***
   Gives us detailed analysis of the log file custom fit as needed by the user, it also gives us detailed analysis in the form of various graphs.
4. ***Auto-Analysis vs Review a log:***

| ***Feature***       | ***Auto Analysis***  | ***Review a Log***                    |
| ------------------- | -------------------- | ------------------------------------- |
| **Purpose**         | Quick health check   | Detailed manual inspection            |
| **Ease of Use**     | Very easy            | Moderate to advanced                  |
| **Detail Level**    | Low to moderate      | High                                  |
| **Format**          | Text-based summary   | Interactive graph viewer              |
| **Ideal For**       | First-look diagnosis | Debugging, tuning, deep investigation |
| **Shows Graphs**    | No                   | Yes                                   |
| **Custom Analysis** | No                   | Yes                                   |

#### LOG Analysis:
1. **AMS Log:**
   - ***AMS Auto Log:***
     
    ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/AMS%20LOG.png?raw=true) 
   - ***Altitude vs Time:***
     ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/AMS%20ALT%20vs%20Time.png?raw=true)
     
     Basic difference between CTUN.Alt (Control Tuning) & AHR2.Alt (Attitude and Heading Reference System (version 2)

| Term         | What It Means                                       | Example Values from Graph     |
| ------------ | --------------------------------------------------- | ----------------------------- |
| **CTUN.Alt** | Commanded altitude relative to home (takeoff point) | 0 to ~60 meters (green line)  |
| **AHR2.Alt** | Actual altitude (absolute above sea level)          | ~842 to 905 meters (red line) |

 - ***Throttle & Battery vs Time consumption:***
   ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/AMS%20Throttle%20vs%20Battery.png?raw=true)   
   - *Volt*: 
    Real-time/inst. battery voltage (in volts).
   - *CurrTot*: 
    Total current consumed over the mission (in mAh or Ah depending on settings).
   - *Throttle Hover ThH:*
    It represents the actual throttle output required for the drone to maintain a stable hover. It is with respect to the thrust to weight ratio of the drone. It's a normalized value ranging from 0 to 1, where 0 corresponds to 0% throttle and 1 represents 100% throttle. Ideally, a ThH value close to 0.5 indicates that the drone is hovering efficiently, utilizing around 50% of its available throttle capacity. However, if the ThH value exceeds 0.7, it may suggest potential issues such as an overweight airframe, underpowered or inefficient motors, or a significant drop in battery voltage leading to reduced thrust output.

   -  ***Battery voltage vs Time:***   
     ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/AMS%20Battery%20volt.png?raw=true)
     
        This image shows just the voltage values of the drone, the spikes here show the alterations in battery voltage. The lower spikes are recorded during the transition between 2 waypoints. This shows that the voltage consumed by the drone is least when transitioning between 2 waypoints. Reason being here the velocity of the drone is also the least.

  - ***Velocity vs Time:***
    ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/AMS%20Speed%20vs%20time.png?raw=true)
    
    The above image shows the graph of Velocity vs Time. On analysis of the graph at each location it is evident that the peak velocity of the drone was recorded in the straight path between the two waypoints, and the lower most peaks of the velocity was recorded at the turns between the waypoints. 

2. **Simulator Log:**
   - ***Simulator Auto Log:***
    ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Simulator%20LOG.png?raw=true)
   - ***Altitude vs Time:***
    ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Alt%20vs%20Time.png?raw=true)
    The pink shade shows the drone being in stabilize mode, after that the turquoise color shows the drone in auto mode. Indicating the drone had ~ 0m altitude i.e., on the ground when in stabilize mode, later it was switched to the Auto mode and followed the path which was fed in the FC. Drone reached a peak of 150m altitude this altitude was reached between waypoint 5 & 6.

   - ***Throttle vs Time:***
    ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Throttle%20Vs%20time.png?raw=true)
    
	    Here we can see the peak throttle detected was 0.48, that took place when the drone took off from ground to its maximum altitude, the later peak throttle was detected just after the 3rd waypoint. Unlike before, here I used ThO which stands for throttle output, it shows the real time throttle (%) commanded by the pilot.
    
   -  ***Battery Consumption vs Time:***
     ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Battery%20current%20vs%20time.png?raw=true)
     
         The above image shows the plot of battery current consumption (mAh) with respect to the flight time.
   
   - ***Battery Voltage  vs Time:***
     ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/voltage%20vs%20time.png?raw=true)
     
        The above graph shows the battery consumption (v) with respect to the flight time. We can see that the drone consumes constant 12.6 volts of battery throughout the flight time. 

   - ***Velocity vs Time:***
     ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/velocity%20vs%20time%20Sim.png?raw=true)
     
        The above graph shows velocity of the drone (m/s) at various time stamps. The peak velocity was found somewhere in the midpoint of 6th and 7th waypoints, and dropped subsequently.

3. **Crash Log:**
   - ***Crash Auto Log:***
    ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Crash%20LOG.png?raw=true)
    Here, 
    -  We can see that the compass calibration- Fail, meaning it wasn't done properly
    - GPS module was physically connected but in the log file it says that No GPS log data that means either the GPS was faulty or the connection was faulty.

   - ***Altitude vs Time:*** 
     ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/Screenshot%202025-05-21%20124728.png?raw=true)
     Here as we can see the altitude AGL values are in -ve, which shouldn't be, this makes us conclude the initial calibration done was faulty. Better calibration and placement of the FC would tackle this issue.

   -  ***Throttle & Battery vs Time:***
    Because of faulty calibration/chosen log settings , throttle and battery data have not been recorded in the log files.

   -  ***Velocity vs Time:***
    Because of faulty calibration/chosen log settings , velocity data has not been recorded in the log files.

4. **3D flight path:**
   ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/3D%20View%20(1).png?raw=true)![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/3D%20View%20(2).png?raw=true)
   The above images show the 3D view of flight path followed by the drone. 
   
##### **Why no animated video?** 
   Mission Planner sometimes exports only the path, waypoints, and position markers, but not an animated tour. This typically happens when the log lacks telemetry timing data, which is essential for generating a time-based animation. Without this data, Mission Planner cannot reconstruct the sequence of movements over time, resulting in a static path instead of a dynamic video. Only `.tlog` files—telemetry logs recorded during flight—contain the detailed time-stamped information required to build an animated video that shows the drone's motion over time.

### **References:**
All the resource materials specified in the task, no other resources used.

---
## **2.7 Intro To ROS 2**
### **Objective:**
- Install, setup **Ubuntu 22.04** and **ROS 2 Humble**.
- Learn the basics of Nodes, Topics, Publishers, and Subscribers.
- Create a Publisher node to send fake Drone Altitude data.
- Create a Subscriber node to read and display the Drone Altitude data in real time.
- Document steps clearly with screenshots and code snippets.
### **Learning:** 

| Command            | Purpose                         | What It Does                                                                                                                             | Effect on Packages                                                         | In Short                                                  |
| ------------------ | ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------- |
| `sudo apt update`  | Fetch and refresh package lists | Downloads the latest package lists from repositories, updating system’s knowledge of available versions                                  | No packages are installed or upgraded                                      | Refresh the package info (like checking for new versions) |
| `sudo apt upgrade` | Upgrade installed packages      | Upgrades all installed packages to their latest versions based on updated package lists; installs available updates for current software | Installed packages get upgraded; no removals or new dependencies installed | Actually download and install the new versions available  |

These nodes communicate with each other via means of Topic. A node would send a message to the  topic and another node would receive the message from the topic. The node that sends the message is the publisher node and the node that receives the message is called as the publisher node. Topics can be thought as a new broadcast where there is no direct response from the listener. But for specific one time requests the ROS nodes use services, services can be thought like making a phone call and asking for a data and waiting for a response before continuing, For more complicated tasks of navigating to a particular locations, ROS uses actions, it's like sending a package with tracking.
***Nodes:***
A node is a program that has access to ROS functionalities and communication tools. It is responsible for a specific process that completes a specific task. Nodes communicate with each other and can print logs to the terminal. We can also have nodes that:
- Create graphical interfaces
- Interact with hardware
- Host a web server
- Call a web server, etc.

***Basic Commands in ROS***
- `mkdrir folder_name` Creates a new folder 
- pressing `Ctrl + C` in a terminal where a ROS node is running kills the node, and stops the running node.
- `rqt_graph` fives us the flowchart of the communication happening between the active/running nodes.
- `clear` clears the terminal
- `ros2 run nameofthepackage_cpp/py nameofthenode` is the syntax for running a node in a packages in ROS 2. {it's _cpp for c++ package & _py for python package}
  Note: Writing the extension of package name i.e., cpp/py is not compulsory 
- `code .` this opens the specific folder in VS Code
- After writing a certain code in terminal and pressing `tab`(on keyboard) gives us the auto-complete options.
### **Major Learning:** 
#### **Installation:**
1. Install and setup Ubuntu 22.04
2. Install ROS 2 Humble
   - Choose binary package installation
   - And then click "Debian Packages"
   - Follow the instructions, i.e., copy-paste the given codes in the ubuntu terminal.
     During the installation there are two types of file available, ROS Desktop installer & ROS Base installer:
     - ***ROS Desktop installer:*** 
       - It has GUI, and used in normal laptops & CPUs as the processor can support the graphical load.
     - ***ROS Base Install (Bare Bones):*** 
       - It has just the communication libraries, command line & no GUI. It is used mostly when the available processing power is limited, i.e., in case of Raspberry Pie etc.
    - Setup the environment by sourcing the setup script.
      ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/ROS%20Sourcing.png?raw=true)
      
    - To source the above location, type `gedit ~/.bashrc` and paste the above location which is to be sourced, i.e., `source /opt/ros/humble/setup.bash`
#### **Creating ROS 2 Workspace:**
1. To install colcon run `sudo apt install python-is-python3 python3-colcon-common-extensions`
2. `cd /usr/share/colcon_argcomplete/hook/` is used to build a workspace in ROS 2. Here "colcon" is the build tool.
3. Click `ls` to view the files within it & then just source the `.bash` script into the source using `gedit ~/.bashrc`. Add another line after the line having source to installation added, in the newly added line paste the path i.e., `usr/share/colcon_argcomplete/hook/Here paste the .bash script` 
4. Hit Save and quit
5. Follow the cmds in the below image:
   ![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/setup%20of%20Workspace.png?raw=true)
#### **Creating ROS 2 Packages:**
Before we start making custom nodes, we first need to create packages. Generally nodes are written inside packages as they allow us to organize the code in a better way, organize the dependencies more efficiently. Follow the below steps to create a ROS 2 package:
1. Go to the created ROS 2 Workspace
2. Change Directory to `src`
3. Create the package using the below syntax:
   `ros2 pkg create package_name --build-type ament_python --dependencies rclpy `
   *Here we are creating a Python node*
   - Note:
     - No spaces allowed in the name of the package
     - Ament is the build system
     - To create a C++ node type `ament_cmake`
     - To create a Python node type `ament_python`
     - `rclpy` is the Python library for ROS 2
#### **Creating ROS 2 Nodes:**
1. Install the ROS extension, Python extension inside VS Code
2. First line of code is `import rclpy`
3. Write the required code
#### **Topics:**
In the below image, talker and listener are the two nodes and chatter is the topic via which the communication takes place. Here the talker node publishes to the chatter topic and the listener node subscribes to the chatter topic. The talker doesn't communicate directly to the listener, it communicates via a topic (chatter) in this case. Multiple nodes can publish or subscribe to the same topic.

![](https://github.com/Asshrayyyy/MARVEL-Aviation-/blob/main/topics%20&&%20nodes.png?raw=true)

Few important cmds for dealing with topics are as follows :
- `ros2 topic list` gives us the list of topics
- `ros2 topic info /actualtopicname` this gives us the type of the topic (what is being sent), number of publishers & number of subscribers. 
- `ros2 interface show typeoftopic/obtainedfrom/abovecmd` this gives us the datatype of the values stored in the topic
- `ros2 topic echo /actualtopicname` after running this node, this would give us the data that is being exchanged via the topics
#### **Task:**
1. First create a workspace, basically a folder to store a particular project so that you can put source files, install files etc., inside it.
2. Go to `src` folder of the workspace & create a package, within this package you create nodes.
   - Go to the `src` of the workspace by, `cd ~/ros2_ws/src` (Ex: `ros2_ws` is the name of the workspace)
   - Create the package, `ros2 pkg create drone_data --build-type ament_python --dependencies rclpy std_msgs`
3. In the files, go inside the `src` of the workspace which is created and then right click, open in terminal. After opening in terminal type `code .` to open the same location in VSC.
4. There will a folder name as same as the  package name we created. Inside the same create another `.py` code name it as a `publisher code` & type the respective publisher code inside it. Once done create another `.py` code this time for subscriber and type the subscriber node code within it.
5. There will be pre-made `setup.py` code, modify this code also accordingly.
6. Once the above steps are done, we need to build and run the code. For this follow the below steps:
   - `cd ~/workspace_namehere`
   - `colcon build`
   - `source install/setup.bash`
   - `ros2 run packagename nodename`
     - For running publisher node: `ros2 run packagename publishernode` [In terminal 1]
     - For running publisher node: `ros2 run packagename subscribernode` [In terminal 2]
7. in the 3rd terminal run `rqt_graph` to see the graphical representation of the nodes & terminals.
   
**The below is the video of me executing, running and performing the tasks:**

<iframe width="560" height="315" src="https://www.youtube.com/embed/iAOt5JZ2T8Y?si=Pp_TVQoO-E8MI9q7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### **References:**
All the resource materials specified in the task, no other resources used.

---
Thank You for going through my lenghty reports!, I hope it served as a good learning & resource material for y'all. 😁
--