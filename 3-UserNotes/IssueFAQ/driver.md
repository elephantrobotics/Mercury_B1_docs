
# 驱动器相关

## 1 关于python

**问： send_base_coords（[x，y，z，rx，ry，rz]， speed） 此 API 中的参数是什么意思？rx、ry 和 rz 对应于欧拉角什么？欧拉角的旋转顺序是什么？每个参数的取值范围是多少？**

- 答：前面数组中的参数是 mercury X1 末端的坐标，speed 是速度。rx、ry 和 rz 应对应 RPY，即分别对应滚动、俯仰和偏航。欧拉角的阶数是 zyx，zyx 是它自己的坐标。x、y、z的取值范围。为-350\~350，-350\~350，-41\~523.9（取值范围未定义，如果超过该范围，将返回逆运动学无解提示），rx、ry、rz的取值范围为-180~180。

**问：不同版本的机械臂的 python api 是否相同？**

- 答：API 是一样的。

## 2 关于ROS
**问：您能提供 rviz 模型的文件和编程示例吗？**

- 答：它可以在我们的 github 上找到。
“https://github.com/elephantrobotics/mercury_ros2”

**问：为什么使用 ROS 启动 rviz 模型文件时，报错权限“/dev/ttyUSB0”？**

- 答：这是因为没有给出串口权限。您应该在终端中键入 sudo chmod 777 端口名称。
  例如：
  ```
  sudo chmod 777 /dev/ttyUSB0
  ```

**问：为什么在运行 ROS 的滑块控件和模型遵循命令时，错误 \_init_() takes exactly 2 arguments (3 given)？**

- 答：pymycobot 库未安装和启动。

**问：使用 ROS 时，为什么打开 rviz 模型后 mercury_B1 角度与模型角度不一致？**

- 答：很有可能mercury_B1的零位没有校准，mercury_B1的零位需要校准。

[← 上一页](../3.4-FAQsandSolutions.md) | [下一页 →](./software.md)