# Software problem

## About robotic arm control

**Question: When sending angles or coordinates to the robotic arm, the robotic arm does not move**

- A: Use `get_angles()` to read the angle of the robotic arm. If the angle return is empty, check whether the robotic arm is powered on. Use `power_on()` to power on the robotic arm; check whether the port number is used. correct.
If there is an angle, check whether the angle exceeds the range of motion. See Table 1. If it exceeds the range, use `release_all_servos()` to relax all joints (note that the joints will fall after relaxing and need to be caught), and align the zero scale lines of joints 1~5 and 7. , 6 joints are 90 degrees perpendicular to the zero scale line. Then use `focus_all_servos()` to lock the joints, then use `set_servo_calibration(1)~set_servo_calibration(7)` to calibrate the zero points of each joint in sequence, and then use `get_angles()` to read the current joint angles. For example, the returned data is [0, 0 , 0, 0, 0, 90, 0], the calibration is successful, otherwise the previous calibration steps are repeated.

<center> Table 1-1 Movement range of each joint angle

| joint | range |
| :----: | :----: |
| J1 | -175 ~ +175 |
| J2 | -65 ~ +115 |
| J3| -175 ~ +175 |
| J4 | -180 ~ +10 |
| J5| -175 ~ +175 |
| J6| -20 ~ + 173 |
| J7| -180 ~ +180 |

</center>

**Q: The camera cannot be turned on**

- A: Open the local camera to see if you can switch to the left and right arm cameras. If a camera cannot be viewed, re-plug the USB port or replace the USB port.
If you can switch to the left and right cameras, check whether the camera port has changed (the port may change after restarting)

**Q: The adaptive gripper cannot be controlled**

- A: Check the power indicator light of the adaptive gripper. When normal, the indicator light should be in a steady state. If the indicator light flashes, please re-plug the connection cable between the gripper and the robotic arm. If the indicator light returns to a steady state, normal.
If the indicator light is always on and still cannot be controlled, use `set_gripper_mode(0)` to change the gripper usage mode.