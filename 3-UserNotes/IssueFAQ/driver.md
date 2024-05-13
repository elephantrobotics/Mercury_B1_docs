# Related

## 1 About python

**Q: Send_base_coords ([x, y, z, rx, ry, rz], Speed) What does the parameters in this API mean? What is RX, RY and RZ corresponding to Euler Kou? What is the rotation order of Euler Horn? What is the value range of each parameter?**

- A: The parameters in the previous array are the coordinates of the end of the Mercury X1, and the Speed ​​is the speed. RX, Ry, and RZ should correspond to the RPY, that is, correspondingly rolling, pitching, and offsets, respectively. The order of the Euler Horn is ZYX, and Zyx is its own coordinates. The value range of x, y, and z.为-350\~350，-350\~350，-41\~523.9（The value range is undefined, and if it is exceeded, the inverse kinematics no solution tip is returned），rx、ry、rz Is in the range of-180 ~ 180.

**Q: Is the Python API of different versions of the robotic arm the same?**

- A: The API is the same.

## 2 About ROS
**Q: Can you provide documentation and programming examples for the rviz model? **

- A: It can be found on our github.
"https://github.com/elephantrobotics/mercury_ros2"

**Q: Why is the permission "/dev/ttyUSB0" error reported when using ROS to start the rviz model file?**

- A: This is because serial port permissions are not given. You should type sudo chmod 777 port name in the terminal.
   For example:
   ```
   sudo chmod 777 /dev/ttyUSB0
   ```

**Q: Why does the error \_init_() take exactly 2 arguments (3 given) when running ROS's slider control and model follow command?**

- A: The pymycobot library is not installed and started.

**Q: When using ROS, why is the angle of mercury_B1 inconsistent with the angle of the model after opening the rviz model?**

- A: It is very likely that the zero position of mercury_B1 is not calibrated, and the zero position of mercury_B1 needs to be calibrated.

[← Previous](./3.4-faqsandsolutions.md) | [Next page →](./software.md)