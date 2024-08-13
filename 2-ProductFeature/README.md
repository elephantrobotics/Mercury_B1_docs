# Robot Parameters Description

> In the first chapter, we explored the product's selling points and design concepts, providing you with a panoramic view of the product's high-level understanding. Now, let's move on to the second chapter - Robot Parameters Description. This chapter will be key to understanding the technical details of the product. Understanding these technical parameters in detail will not only help you fully recognize the product's advanced features and practicality but also ensure that you can effectively utilize these technologies to meet your specific needs.

## 1 Machine Parameters

| Index | Parameter |
|:------------: |:----------------------------: |
| Chinese Name | Mercury B1 Dual-arm Robot |
| Model | Mercury B1 |
| Product Size | 200\*192.5*537mm |
| Degrees of Freedom | 17 |
| Maximum Working Radius | 8 hours |
| Maximum Load | 1KG |
| Arm Repeatability | ±0.05 mm |
| Net Weight | 8KG |
| Working Voltage | 24V |
| Repeatability | +-0.05mm |
| Reduction Mechanism | Harmonic Reducer |
| Joint Brake Type | Electromagnetic Friction Plate |
| CPU | 6-core Arm v8.2 64-bit CPU |
| GPU | 384-core Volta™ GPU |
| Computing Power | 21 TOPS |
| Material | Carbon Fiber, Aluminum Alloy, Engineering Plastics |
| 3D Camera | Obi Nakakotsu Deeyea |
| Microphone Array | Linear 4-microphone, 5 meters 180° pickup |
| IO | 24V 6 inputs, 6 outputs |
| Screen | 9-inch Touch Screen |
| Communication Methods | CAN bus/WIFI/Ethernet/Bluetooth/USB/Serial Port |

## 2 Basic Software Function Support

| Function/Development Environment | Purpose |
| :------------: | :--------: |
| Free Movement | Supported |
| Joint Movement | Supported |
| Cartesian Movement | Supported |
| Trajectory Recording | Supported |
| Wireless Control | Supported |
| Emergency Stop | Supported |
| Windows | Supported |
| Linux | Supported |
| MAC | Supported |
| ROS 1 | Supported |
| Python | Supported |
| C++ | Supported |
| C# | Supported |
| JavaScript | Supported |
| myblockly | Supported |
| Arduino | Supported |
| mystudio | Supported |
| Serial Control Protocol | Supported |
| TCP/IP | Supported |
| MODBUS | Supported |

---

# 3 Control Core Parameters

### Main Controller Specifications

| Index | Parameter |
| :--------------:| :----------------: |
| Main Control | Jetson Xavier |
| Main Model | Jetson Xavier NX |
| Central Processor | 6-core NVIDIA Carmel ARM®v8.2 64-bit CPU <br> 6MB L2 + 4MB L3 |
| Graphics Processor | 384-core NVIDIA Volta™ GPU with 48 Tensor Cores |
| Computing Power | 21 TOPS |
| Storage | 16 GB eMMC 5.1 |
| CSI Camera | 2 CSI Cameras |
| Network | 10/100/1000 BASE-T Ethernet |
| USB Ports | 1 USB 3.2 2.0 (10 Gbps) <br> 2 USB 2.0 Ports |
| Other Inputs/Outputs | 2 UART Serial Ports |

### Left and Right Arm Sub-controller Specifications

| Index | Parameter |
| :---------------: | :----------------: |
| Sub-control | Left and Right Arm Sub-control |
| Sub-control Model | ESP32 |
| Core Parameters | 240MHz dual core. <br> 600 DMIPS, 520KB SRAM. <br> Wi-Fi, dual mode Bluetooth |
| Sub-control Flash | 4MB |
| LED Display | 5X5 RGB |

---

# 4 Structural Dimensions Parameters

> The units of distance and angle in this chapter are millimeters.

## Product Size and Working Space
When choosing the installation location of the robot, it is important to consider the cylindrical space directly above and below the robot and avoid moving the tool towards the cylindrical space as much as possible. This is because it will cause the joints to rotate too fast when the tool moves slowly, resulting in low robot efficiency and difficult risk assessment.

## Dual-arm End Flange Dimensions
<center>
<img src="../resources/2-ProductFeature/末端法兰.png" width="400" height="auto" />
</center>
<br>
<center>
Figure 2.3.4 End Dimensions
</center>

---

# Electrical Characteristics Parameters

## Base Interface Overview

<center>
<img src="./../resources/2-ProductFeature/底座接口总览.jpg "
width="400" height="auto" />
<br>
Figure 1 Basic Interface Diagram
</center>

## Base Interface Description

| Number | Interface | Definition | Features | Notes |
|:----:|:--------------:|:---------:|:-----------------:|:----------------:|
| 1 | Emergency Stop Interface | Stop | Emergency Stop Circuit Interface | |
| 2 | DC/IO Interface | 24V | DC 24V | DC 24V Output |
| | | OUT1 | Digital Output Signal 1~6 | Only output in PNP mode |
| | | OUT2 | | |
| | | OUT3 | | |
| | | OUT4 | | |
| | | OUT5 | | |
| | | OUT6 | | |
| | | GND | GND | |
| 3 | DC/IO Interface | GND | GND | |
| | | IN6 | Digital Input Signal 1~6 | Only enter NPN mode |
| | | IN5 | | |
| | | IN4 | | |
| | | IN3 | | |
| | | IN2 | | |
| | | IN1 | | |
| | | 24V | DC 24V | DC 24V Input |
| 4 | Ethernet Port | Ethernet | Ethernet Communication Interface | |
| 5 | Power Input Interface | DC 24V Input | DC 24V Input | |
| 6 | Switch | Power Switch | Controls the on/off of the input power | With light (light on) |
| 7 | R-USB | Right Arm USB | Connects external camera via USB | |
| 8 | L-USB | Left Arm USB | Connects external camera via USB | |
| 9 | USB 3.0 | USB 3.0*2 | Connects external devices or USB drives |

---

## End Interface Overview
<center>
<img src="./../resources/2-ProductFeature/左臂末端图.jpg" width="400" height="auto" />
<br>
Figure 5 Left Arm End Diagram
<br>
<img src="./../resources/2-ProductFeature/右臂末端图.jpg" width="400" height="auto" />
<br>
Figure 6 Right Arm End Diagram
<br>
</center>

## End Interface Description
| Number | Interface | Definition | Function | Notes |
|:------:|:----------------:|:-----------:|:-------------------:|:------------------:|
| 6 | 4-pin USB Terminal | External Interface | Connects Camera | |
| 7 | M8 Aviation Socket | End Tool IO Interface | Interacts with External Devices | |

#### As shown in the figure is the M8 aviation socket I/O diagram, the Mercury B1 robot provides one input and two outputs.
<center>
<img src="../resources/2-ProductFeature/机械臂末端工具说明.png " width="" height="auto" />
<br>
The definitions of each tool I/O port are shown in the table below. Note that the tool I/O is PNP type whether it is input or output, and the wiring method is the same as the bottom output interface.
</center>

| Number | Signal | Explanation | Matching M8 Wire Color |
| :------: | :------: | :-----------------------: | :--------------------------: |
| 1 | GND | DC 24V Negative | White |
| 2 | OUT1 | Tool Output Interface 1 | Brown |
| 3 | OUT2 | Tool Output Interface 2 | Green |
| 4 | 485A | Reserved, Not Developed | Yellow |
| 5 | 24V | DC 24V Positive | Gray |
| 6 | IN1 | Tool Input Interface 1 | Pink |
| 7 | IN2 | Tool Input Interface 2 | Blue |
| 8 | 485B | Reserved, Not Developed | Purple |

#### USB Terminal: Used to connect the camera

If you have read all the content of this chapter, you can continue to the next chapter.

[← Previous Chapter](../1-ProductIntroduction/README.md) | [Next Chapter →](../3-UserNotes/README.md)
