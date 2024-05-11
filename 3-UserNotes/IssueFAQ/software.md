# 软件问题

## 关于ROS1

**问:终端切换到~/catkin_ws/src，使用git安装更新mercury_ros时，目标路径“mercury_x1_ros”已经存在。原因是什么?**

- 答:这意味着在~/catkin_ws/src中已经有一个“mercury_ros”包了。需要提前删除，然后重新执行git操作。

**问: rosrun运行时，终端错误提示“could not open port /dev/ttyUSB0: Permission: '/dev/ttyUSB0'”。为什么?**

- 答:串口权限不足。在终端输入“sudo chmod 777 /dev/ttyUSB0”，授予权限。

**问:为什么ROS程序不能在VSCode中运行?**

- 答:由于VSCode终端无法加载到ROS环境中，需要在系统终端中运行。

**问: rosrun运行时，终端提示“无法注册主节点[http://localhost:11311]:主节点可能尚未运行”。我会继续努力的。”原因是什么?**

- 答:运行ROS程序前，需要打开ROS节点，在终端中输入“roscore”。

**问: rosrun运行时，终端错误提示“could not open port /dev/ ttyusb0: No such file or directory: '/dev/ttyUSB1'”。为什么?**

- 答:串口错误。需要确认当前机械臂的实际串口。可以通过` ls /dev/tty* `查看。

**问:在Ubuntu18.04中，' catkin_make '构建代码失败，终端提示' Project 'cv_bridge'指定'/usr/include/opencv'作为包含目录，没有找到。和其他错误信息**

- 答:配置文件中的OpenCV路径与系统实际路径不匹配。你需要使用sudo命令修改配置文件(路径为“/opt/ros/melodic/share/cv_bridge/cmake/cv_bridgeConfig.cmake”)。系统的实际OpenCV路径位于“/usr/include/”路径下。

**问:只需克隆mercury_ros包，然后直接运行rosrun程序。出现诸如“package”mercury_ros“not found”之类的错误或诸如无法找到文件之类的错误?**

- 答:新克隆的mercury_ros需要构建ROS环境编译的代码。终端输入

```
bash
cd ~/catkin_ws/
catkin_make
source devel/ setup.bash
```

## 关于机械臂控制

**问:给机械臂发送角度或坐标机械臂没有运动**

- 答：使用`get_angles()`读取机械臂的角度，若角度返回为空，则检查机械臂是否上电，使用`power_on()`对机械臂进行上电使能；检查端口号是否使用正确。
若有角度，查看角度是否超出运动范围见表1，如果超出范围，使用`release_all_servos()`放松所有关节（注意关节放松后会下坠，需要接住），对齐1~5、7关节零刻度线，6关节与零刻度线90度垂直。再使用`focus_all_servos()`锁定关节，再使用`set_servo_calibration(1)~set_servo_calibration(7)`依次校准各关节零点，再使用`get_angles()`读取当前关节角度，如返回数据为[0, 0, 0, 0, 0, 90, 0]则为校准成功，否则重复之前的校准步骤。

<center> 表1-1 各关节角度可运动范围

|   关节   | 范围   |
|  :----:  | :----:  |
| J1  | -175 ~ +175 |
| J2  | -65 ~ +115 |
| J3| -175 ~ +175 |
| J4  | -180 ~ +10 |
| J5| -175 ~ +175 |
| J6| -20 ~ + 173 |
| J7| -180 ~ +180 |

</center>

**问:摄像头无法打开**

- 答：打开本地相机查看是否可以切换到左右臂摄像头，如有某个摄像头无法查看，则重新拔插USB口或者更换USB口。
若可以切换到左右摄像头，检查摄像头端口是否发生变化(在重启后，端口可能发生变化)

**问:自适应夹爪无法控制**

- 答：查看自适应夹爪的电源指示灯，正常时指示灯应为常亮状态，若指示灯出现闪烁情况，请重新拔插夹爪与机械臂的连接线，指示灯恢复常亮状态则正常。
若指示灯为常亮状态仍无法控制，使用`set_gripper_mode(0)`更改夹爪使用模式。
