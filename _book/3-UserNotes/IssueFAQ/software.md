# Software issues

## About ROS1

**Question: When the terminal switches to ~/catkin_ws/src and uses git to install and update mercury_ros, the target path "mercury_ros" already exists. what is the reason?**

- A: This means there is already a "mercury_ros" package in ~/catkin_ws/src. You need to delete it in advance and then perform the git operation again.

**Question: When rosrun is running, the terminal error prompts "could not open port /dev/ttyUSB0: Permission: '/dev/ttyUSB0'". Why?**

- A: The serial port permissions are insufficient. Enter "sudo chmod 777 /dev/ttyUSB0" in the terminal to grant permissions.

**Question: Why can’t ROS programs run in VSCode?**

- A: Since the VSCode terminal cannot be loaded into the ROS environment, it needs to be run in the system terminal.

**Question: When rosrun is running, the terminal prompts "Unable to register the master node [http://localhost:11311]: The master node may not be running yet." I will continue to work hard. "what is the reason?**

- A: Before running the ROS program, you need to open the ROS node and enter "roscore" in the terminal.

**Question: When rosrun is running, the terminal error prompts "could not open port /dev/ ttyusb0: No such file or directory: '/dev/ttyUSB1'". Why?**

- A: Serial port error. It is necessary to confirm the actual serial port of the current robot arm. Can be viewed via ` ls /dev/tty* `.

**Q: In Ubuntu18.04, 'catkin_make' fails to build the code, and the terminal prompts that 'Project 'cv_bridge' specifies '/usr/include/opencv' as the include directory and is not found. and other error messages**

- A: The OpenCV path in the configuration file does not match the actual path of the system. You need to use the sudo command to modify the configuration file (the path is "/opt/ros/melodic/share/cv_bridge/cmake/cv_bridgeConfig.cmake"). The actual OpenCV path of the system is located under the "/usr/include/" path.

**Q: Just clone the mercury_ros package and run the rosrun program directly. Getting errors like "package"mercury_ros"not found" or errors like file cannot be found?**

- A: The newly cloned mercury_ros needs to build the code compiled by the ROS environment. Terminal input

```
bash
cd ~/catkin_ws/
catkin_make
source devel/ setup.bash
```

## About robotic arm control

**Question: When sending angles or coordinates to the robotic arm, the robotic arm does not move**

- A: Use `get_angles()` to read the angle of the robotic arm. If the angle return is empty, check whether the robotic arm is powered on. Use `power_on()` to power on the robotic arm; check whether the port number is used. correct.
If there is an angle, check whether the angle exceeds the range of motion. See Table 1. If it exceeds the range, use `release_all_servos()` to relax all joints (note that the joints will fall after relaxing and need to be caught), and align the zero scale lines of joints 1~5 and 7. , 6 joints are 90 degrees perpendicular to the zero scale line. Then use `focus_all_servos()` to lock the joints, then use `set_servo_calibration(1)~set_servo_calibration(7)` to calibrate the zero points of each joint in sequence, and then use `get_angles()` to read the current joint angles. For example, the returned data is [0, 0 , 0, 0, 0, 90, 0], the calibration is successful, otherwise the previous calibration steps are repeated.

<center> Table 1-1 Movement range of each joint angle</center>

| joint | range |
| :----: | :----: |
| J1 | -175 ~ +175 |
| J2 | -65 ~ +115 |
| J3| -175 ~ +175 |
| J4 | -180 ~ +10 |
| J5| -175 ~ +175 |
| J6| -20 ~ + 173 |
| J7| -180 ~ +180 |



**Q: The camera cannot be turned on**

- A: Open the local camera to see if you can switch to the left and right arm cameras. If a camera cannot be viewed, re-plug the USB port or replace the USB port.
If you can switch to the left and right cameras, check whether the camera port has changed (the port may change after restarting)

**Q: The adaptive gripper cannot be controlled**

- A: Check the power indicator light of the adaptive gripper. When normal, the indicator light should be in a steady state. If the indicator light flashes, please re-plug the connection cable between the gripper and the robotic arm. If the indicator light returns to a steady state, normal.
If the indicator light is always on and still cannot be controlled, use `set_gripper_mode(0)` to change the gripper usage mode.