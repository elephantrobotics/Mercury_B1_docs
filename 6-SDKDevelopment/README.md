# Software Development Guide

## 1 Operating Environment

The Mercury B1 humanoid robot is developed and used based on the built-in Ubuntu system.

## 2 Development Environment

To meet the diverse application needs of the robot in different scenarios, we have adapted the robot to various programming languages. So far, we have adapted the following mainstream programming languages, and we believe you can use any of these languages for development. Please be sure to follow the instructions carefully. Any missed steps may result in the corresponding language not running successfully. We wish you a smooth experience with the robot.

- [Python](./6.1-Python/README.md)<br>
  Our robot supports Python, and the development of the Python API library is becoming more and more complete. The robot's joint angles, coordinates, gripper, and other aspects can be controlled through Python.<br>

- [ROS1](./6.2-ROS1/README.md)<br>
  ROS (Robot Operating System) is an open-source robot operating system that provides infinite possibilities for robot development and control. Our robot can be controlled through ROS's rich control functions in a modular way. Whether it is joint control, path planning, or perception feedback, ROS provides corresponding tools and libraries, making the control process more flexible and efficient.</br>
- [ROS2](./6.3-ROS2/README.md)<br>
  ROS 2 (Robot Operating System 2) is a flexible software framework designed for robot software development. Our robot can use the hardware abstraction, device drivers, library functions, visualization tools, message passing, and package management services and functions provided by ROS 2, making application development more efficient and modular.</br>
<!-- - [Communication](./5.4-DevelopmentBasedOnCommunicationProtocolPackage//5.4.1-CommunicationDoc.md)<br>
  If you have some understanding of information theory, coding, and robot communication functions, then you should understand that all communication originates from data transmission. To facilitate user operation of the robot, we have opened a communication protocol based on serial communication. You can use a serial assistant or encapsulate it in any programming language you are familiar with to control the robot. -->

---

[← Previous Chapter](../4-FirstInstallAndUse/README.md) | [Next Page →](../6-SDKDevelopment/6.1-Python/README.md)