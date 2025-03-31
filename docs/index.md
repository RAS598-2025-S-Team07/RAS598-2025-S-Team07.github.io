# Welcome to the Multipurpose Macro Load Bearing Assistive Follower Robot Project

**Team:** 07  
**Course:** RAS 598 Experimentation and Deployment of Robotic Systems, Arizona State University

## Team Members

### Rhutvik Pachghare
Pursuing a master's degree in robotics and autonomous systems, with a degree in Electrical Engineering and experience as a team lead software developer, specializing in cloud computing and multiple development languages.

### Mohammad Nasr
Robotics and autonomous systems PhD student specializing in designing Bio-inspired hearing for robotic platforms.

### Shashank Sing Deo
B.Tech in Mechanical Engineering, worked as systems and integration engineer with Evage motors designing N1 and M3 category vehicles for Indian, Middle east and European markets.

## Introduction
This project seeks to explore how a mobile robotic system can effectively follow and assist a user while maintaining situational awareness through obstacle detection and user recognition. Specifically, we aim to develop a follower robot using a TurtleBot equipped with a depth camera and Lidar. This system will enable hands-free transportation of small items (e.g., groceries, shopping bags, or tools) and assist with tasks like carrying a camera for photography or videography. Through this research, we hope to contribute to the advancement and normalization of Assistive Robots Technology in everyday life.

![Project Idea](/assets/images/IMG_9859.PNG "functional depiction of the idea")

## Sensor Integration

The assistive follower robot will utilize a combination of the depth camera and LiDAR to achieve robust user tracking and situational awareness. The depth camera will be used for user recognition and tracking, while LiDAR will be used to ensure the robot maintains an optimal following distance. Additionally, LiDAR can be used for 360-degree obstacle detection and environmental mapping, allowing the robot to navigate dynamically changing environments safely.

![Sensor Integration](/assets/images/IMG_9871.PNG "Sensor Integration")

## Interaction

The TurtleBot 4 is equipped with a depth camera, LiDAR, and a Raspberry Pi board, enabling effective interaction and control. Due to the limited field of view of the depth camera and the desire to reduce computational load on the Raspberry Pi, we have adopted shoe detection as a lightweight and focused approach for user identification. A custom-trained model will detect the user's shoes, allowing us to estimate their direction relative to the image center. The image data will be processed externally on a PC or online on the raspberry pi, and the results will be used to guide robot's motion.

LiDAR will be used for 360-degree obstacle detection and distance maintenance, and will play a central role in real-time gap-finding navigation. In situations where the robot is unable to find a viable local path using the gap-finding algorithm, it will fall back on a pre-built SLAM map to determine an alternative route. This layered approach allows the robot to adapt intelligently to dynamic and complex environments.

![Interaction](/assets/images/IMG_9870.PNG "Interaction between various components")

## Control and Autonomy

The depth camera will be used to detect the user's shoes in real-time, providing a simple yet effective method for user recognition and direction estimation. The image stream will be processed externally on our laptop or online on the raspberry pi, where a custom-trained model will identify the location of the shoes in the frame. This information will be translated into the user’s direction relative to the robot and communicated back to the TurtleBot over ROS2, allowing it to adjust its motion accordingly.

LiDAR will be the primary sensor for dynamic obstacle detection, gap-finding, and distance maintenance. It will also help refine the robot’s understanding of the user’s position by correlating the visual direction from the camera with the LiDAR scan to estimate the user’s distance. In cases where the gap-finding algorithm cannot identify a safe path forward, the robot will utilize a prebuilt SLAM map to determine an alternative route around obstacles, ensuring reliable and adaptive navigation in cluttered environments.

## Preparation Needs

### What do you need to know to be successful?
- Learn to calibrate and operate the hardware like camera, LiDAR, Raspberry Pi
- Machine learning tools or OpenCV for optimal image processing
- Data filtering
- Control Logic and data flow

### Which of those topics do you need to cover in class?
- Data filtering
- Control Logic and data flow

## Final Demonstration

Conditions change in any environment. How will your robot handle variability in its environment?
- Potential environmental variabilities include lighting conditions, the user’s relative direction with respect to the robot, and narrow gaps smaller than the robot’s diameter.
- Changes in lighting conditions can affect image processing and user recognition accuracy. To address this, more advanced image processing algorithms that are robust to lighting variations will be explored.
- In scenarios where the robot encounters narrow gaps that are smaller than its diameter, the robot needs predefined behavior. In our case, The robot will use SLAM and mapping as an alternative mean of motion planning.
- To maintain accurate user tracking during movement, an optimal update rate for user position data will be determined. This will allow the robot to dynamically adjust the LiDAR beam it uses for distance keeping and movement direction correction, ensuring responsive and adaptive following behavior.

## Testing & Evaluation Plan

### Scenario 1: Linear and Turning Motion
The robot follows the person in a straight line and takes turns as the person takes turns in a 2000mm x 1500mm test area divided into 500mm vertical sections.

![Test Area 1](/assets/images/IMG_9868.PNG "Test Area 1")

### Scenario 2: Random Path Tracking
The robot must work autonomously and comprehend random paths traveled by the person. We plan to place start and stop markers for the target randomly in the test area with obstacles like traffic cones.

![Test Area 2](/assets/images/IMG_9867.PNG "Test Area 2")

### Scenario 3: Obstacle Detection and Alternate Path
The robot may encounter obstacles in its path and must devise a new path to reach the target person.

![Test Area 3](assets/images/IMG_9869.PNG "Test Area 3")

## Impact

This project will advance assistive robotics by developing a follower robot that can safely navigate and help users in dynamic environments. It will help us learn advanced ROS2 communication, multi-sensor data fusion, and computer vision for real-time processing. We will also gain experience in dynamic path planning and obstacle avoidance. The knowledge gained will enhance our skills in robotics and autonomy. Our work can also contribute to course development by serving as an example helping future students.

## Project Advisor

**Dr. Daniel Aukes**  
Dr. Daniel Aukes is an Associate Professor and the director of the IDEAlab. His research investigates the nexus of design, manufacturing, and data-driven decision-making to develop robots that can operate in niche environments, with a focus on affordability and accessibility. IDEALab projects focus on new tools for designing robots by pairing emerging fabrication techniques and new materials with analytical and simulation-based methods for understanding the behavior of complex systems. 

## Weekly Milestones

| Week | Hardware Integration | Interface Development | Sensors | Controls & Autonomy |
|------|-----------------------|-----------------------|---------|---------------------|
| Week 7 | Set up TurtleBot 4, all team members access, configuration | N/A | Test data publishing from depth camera and LiDAR, IMU on ROS2 topics | N/A |
| Week 8 | Calibrate depth camera for user recognition; Configure LiDAR | Learn Rviz and Gazebo | Verify sensor data accuracy and publish on ROS2 topics | N/A |
| Week 9 | Ensure smooth data streaming to external PC for image processing | Use data visualization in real time with Rviz | Implement LiDAR, Depth Camera data | N/A |
| Week 10 | Finalize hardware setup and connections | Implement interaction features: mode switching, emergency stop, and distance adjustment | Implement LiDAR, Depth Camera data | Try object avoidance |
| Week 11 | N/A | User recognition modeling | Implement data acquisition and filtering for depth camera and LiDAR | Implement object avoidance |
| Week 12 | N/A | User recognition modeling | Real time image streaming and prediction | N/A |
| Week 13 | N/A | Real time user position update | Integrate sensor fusion | Implement motion control using user position feedback, and LiDAR data |
| Week 14 | N/A | N/A | Final sensor tuning and data visualization | System integration testing and debugging |
| Week 15 | Test Hardware in Demo Room | Test interaction features in Demo Room | Validate sensor accuracy and reliability | Final Test control logic and decision-making in dynamic environments |
| Week 16 | Demo | Demo | Demo | Demo |
