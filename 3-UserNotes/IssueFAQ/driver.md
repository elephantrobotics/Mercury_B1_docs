# Related

## 1 About python

**Q: Send_base_coords ([x, y, z, rx, ry, rz], Speed) What does the parameters in this API mean? What is RX, RY and RZ corresponding to Euler Kou? What is the rotation order of Euler Horn? What is the value range of each parameter?**

- A: The parameters in the previous array are the coordinates of the end of the Mercury X1, and the Speed ​​is the speed. RX, Ry, and RZ should correspond to the RPY, that is, correspondingly rolling, pitching, and offsets, respectively. The order of the Euler Horn is ZYX, and Zyx is its own coordinates. The value range of x, y, and z.为-350\~350，-350\~350，-41\~523.9（The value range is undefined, and if it is exceeded, the inverse kinematics no solution tip is returned），rx、ry、rz Is in the range of-180 ~ 180.

**Q: Is the Python API of different versions of the robotic arm the same?**

- A: The API is the same.


[← Previous](./3.4-faqsandsolutions.md) | [Next page →](./software.md)