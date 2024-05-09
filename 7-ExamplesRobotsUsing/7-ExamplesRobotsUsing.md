# 7 Robot arm usage scenario case

This chapter presents classic robotic arm use cases to demonstrate the application of the product in representative scenarios. This includes typical applications of robotic arms in different fields, highlighting the product's versatility and applicability. Through these cases, users can gain an in-depth understanding of the flexibility and performance of the robotic arm in practical applications, providing a reference for their application in specific scenarios.

**1. Painting case:**

```python
from pymycobot.mycobot import MyCobot
import time
import math

#Create a MyCobot instance and specify the serial port and baud rate
mc = MyCobot('COM3',115200)

#Send the target coordinate point to move the robot arm to the specified position
mc.send_coords([52.9, -64.4, 409.7, -91.23, -0.25, -89.81], 50, 0)
# Pause 2 seconds
time.sleep(2)

#Send the target coordinate point to move the robot arm to another specified position
mc.send_coords([21.5, 145.5, 233.6, -89.72, 19.19, 13.45], 50, 0)
# Pause 2 seconds
time.sleep(2)

# Send the target coordinate point cyclically to make the robot arm move in a circular trajectory
for i in range(1, 361):
     x = 21.5 + 30 * math.cos(i / 180.0 * math.pi)
     y = 145.5 + 30 * math.sin(i / 180.0 * math.pi)
     mc.send_coords([x, y, 233.6, -89.72, 19.19, 13.45], 100, 0)
     # Pause 0.7 seconds
     time.sleep(0.7)

#Send the target coordinate point to return the robot arm to the initial position
mc.send_coords([52.9, -64.4, 409.7, -91.23, -0.25, -89.81], 50, 0)
‵‵‵

**2. Dancing case:**

​```python
from pymycobot.mycobot import MyCobot
import time

if __name__ == '__main__':
     #Create a MyCobot instance and specify the serial port and baud rate
     mc = MyCobot('COM3',115200)

     # Set the start time
     start = time.time()
     # Let the robotic arm reach the specified position
     mc.send_angles([-1.49, 115, -153.45, 30, -33.42, 137.9], 80)
     # Determine whether it reaches the specified location
     while not mc.is_in_position([-1.49, 115, -153.45, 30, -33.42, 137.9], 0):
         # Let the robot arm resume movement
         mc.resume()
         # Let the robot arm move for 0.5s
         time.sleep(0.5)
         # Pause the robot arm movement
         mc.pause()
         # Determine whether the move has timed out
         if time.time() - start > 3:
             break
     # Set start time
     start = time.time()
     # Let the movement continue for 30 seconds
     while time.time() - start < 30:
         # Let the robotic arm reach the position quickly
         mc.send_angles([-1.49, 115, -153.45, 30, -33.42, 137.9], 80)
         # Set the color of the light to [0,0,50]
         mc.set_color(0, 0, 50)
         time.sleep(0.7)
         # Let the robotic arm reach the position quickly
         mc.send_angles([-1.49, 55, -153.45, 80, 33.42, 137.9], 80)
         # Set the color of the light to [0,50,0]
         mc.set_color(0, 50, 0)
         time.sleep(0.7)
```

**3. Wood block transport case:**

```python
from pymycobot import PI_PORT, PI_BAUD
import time
def gripper_test(mc):
Print("Start check IO part of api\n")
# Detect whether the gripper is moving
flag = mc.is_gripper_moving()
Print("Is gripper moving: {}".format(flag))
time.sleep(1)

# Set the current position to (2048).
​ # Use it when you are sure you need it.
# Gripper has been initialized for a long time. Generally, there
# is no need to change the method.
# mc.set_gripper_ini()
# Set joint point 1 and let it rotate to the position 2048
mc.set_encoder(1, 2048)
time.sleep(2)
# Set six joint positions and let the robotic arm rotate to this position at a speed of 20

mc.set_encoders([1024, 1024, 1024, 1024, 1024, 1024], 20)
# mc.set_encoders([2048, 2900, 2048, 2048, 2048, 2048], 20)
# mc.set_encoders([2048, 3000,3000, 3000, 2048, 2048], 50)
time.sleep(3)
# Get the position information of joint point 1
Print(mc.get_encoder(1))
# Set the clamping jaw to rotate to the position 2048
mc.set_encoder(7, 2048)
time.sleep(3)
# Set the gripper to rotate to the 1300 position
mc.set_encoder(7, 1300)
time.sleep(3)

# Let the gripper reach the 2048 state at a speed of 70. 2048 will report an error, so change it to 255.
mc.set_gripper_value(255, 70)
time.sleep(3)
# Let the gripper reach the 1500 state at a speed of 70. An error will be reported at 1500, so it is changed to 255.
mc.set_gripper_value(255, 70)
time.sleep(3)
​
num=5
while num>0:
​ ​ #Set the state of the clamping claw and let it quickly open the claw at a speed of 70
        mc.set_gripper_state(0, 70)
time.sleep(3)
          #Set the state of the clamping claw so that it can quickly close the claws at a speed of 70
         mc.set_gripper_state(1, 70)
time.sleep(3)
num-=1

# Get the value of the gripper
Print("")
Print(mc.get_gripper_value())
# mc.release_all_servos()

if __name__ == "__main__":
#Create a MyCobot instance and specify the serial port and baud rate
     mc = MyCobot('COM3',115200)

mc.set_encoders([2048, 2048, 2048, 2048, 2048, 2048], 20)
time.sleep(3)
gripper_test(mc)

```