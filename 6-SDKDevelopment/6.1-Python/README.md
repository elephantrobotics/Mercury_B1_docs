# Environment Configuration

> pymycobot is a Python library developed by Elephant Robot for robot control.

## Linux

The system comes pre-installed with Python 3.8.10 and the `pymycobot` control library, so users do not need to install it themselves.

### Installing pymycobot

You can install pymycobot by entering the following command in the terminal:
````bash
pip install pymycobot
````

### Uninstalling pymycobot

You can uninstall pymycobot by entering the following command in the terminal:
````bash
pip uninstall pymycobot
````

### Updating pymycobot

You can update pymycobot by entering the following command in the terminal:
````bash
pip install pymycobot -U
````

## Windows

### 1.1 Installing Python

> **Note:** Before installation, check the operating system of your PC. Right-click on the "My Computer" icon and select "Properties". Install the corresponding Python version.
>
> <img src="../../resources/6-SDKDevelopment/image/operatingsystemchecking1.jpg" alt="7.1.1-1" style="zoom:50%;" />
>
> <img src="../../resources/6-SDKDevelopment/image/operatingsystemchecking2.jpg" alt="7.1.1-1" style="zoom:50%;" />

* **Go to http://www.python.org/download/ to download Python.**
* **Click "Download" to start downloading. Check "Add Python 3.10 to PATH". Click "Install Now" to start the installation.**

<img src="../../resources/6-SDKDevelopment/image/pythoninstall1.jpg" alt="7.1.1-1" style="zoom:50%;" />

<img src="../../resources/6-SDKDevelopment/image/pythoninstall2.jpg" alt="7.1.1-1" style="zoom:50%;" />

<img src="../../resources/6-SDKDevelopment/image/pythoninstall3.jpg" alt="7.1.1-1" style="zoom:50%;" />

* **Download and installation complete.**
   <img src="../../resources/6-SDKDevelopment/image/pythoninstall4.jpg" alt="7.1.1-1" style="zoom:50%;" />

### 1.2 Running Python
Open the Command Prompt window (Win+R, type "cmd" and press "Enter"). Type "Python".

**Successful Installation:**

<img src="../../resources/6-SDKDevelopment/image/successfulinstallation.jpg" alt="7.1.1-1" style="zoom:50%;" />

Seeing this prompt on the screen means that Python has been successfully installed. The prompt ">>>" indicates the Python interactive environment. If you enter a piece of Python code, you will get the execution result immediately.

**Error Report:**

If you enter an incorrect command, such as "pythonn", the system may report an error.

<img src="../../resources/6-SDKDevelopment/image/installerror.jpg" alt="7.1.1-1" style="zoom:67%;" />

> **Note:** Generally, this error is caused by insufficient environment configuration. Refer to **1.3 Environment Configuration** to solve the problem.

### 1.3 Environment Variable Configuration
Windows follows the Path environment variable settings to search for **python.exe**. Otherwise, an error will be reported. If you did not check "Add Python 3.9 to PATH" during installation, you need to manually add the path where python.exe is located to the environment variables or re-download Python. Remember to check "Add Python 3.9 to PATH".

Follow these steps to manually add Python to the environment variables.

* Right-click on the "My Computer" icon --> Properties -> Advanced System Settings -> Environment Variables

<img src="../../resources/6-SDKDevelopment/image/environment configuration.jpg" alt="7.1.1-1" style="zoom:50%;" />

* Environment variables include user variables and system variables. For user variables, users can use the programs they downloaded through the "cmd" command. Write the absolute path of the target program into the user variables.

<img src="../../resources/6-SDKDevelopment/image/user variable1.jpg" alt="7.1.1-10" style="zoom:50%;" />

<img src="../../resources/6-SDKDevelopment/image/user variable2.jpg" alt="7.1.1-11" style="zoom:50%;" />

* After configuration is complete, open the Command Prompt window (Win+R; type "cmd" and press "Enter"), and then type "Python".

<img src="../../resources/6-SDKDevelopment/image/user variable3.jpg" alt="7.1.1-7" style="zoom:67%;" />

### 2 Installing PyCharm

PyCharm is a powerful, cross-platform Python editor. Follow these steps to download and install PyCharm.

Go to **[PyCharm](http://www.jetbrains.com/pycharm/download/#section=windows)** to download PyCharm.

#### 2.1 Download and Install

Official website view:

<img src="../../resources/6-SDKDevelopment/image/pycharmdownload1.jpg" alt="7.1.1-7" style="zoom:67%;" />

It is recommended to install the free version.

* Click "Next":

<img src="../../resources/6-SDKDevelopment/image/pycharmdownload2.jpg" alt="7.1.1-7" style="zoom:67%;" />

* Select options according to your needs, then select "Next":

<img src="../../resources/6-SDKDevelopment/image/pycharmdownload3.jpg" alt="7.1.1-7" style="zoom:67%;" />

* Click "Install":

<img src="../../resources/6-SDKDevelopment/image/pycharmdownload4.jpg" alt="7.1.1-7" style="zoom:67%;" />

* Installation:

<img src="../../resources/6-SDKDevelopment/image/pycharmdownload5.jpg" alt="7.1.1-7" style="zoom:67%;" />

* Click "Finish"

   <img src="../../resources/6-SDKDevelopment/image/pycharmdownload6.jpg" alt="7.1.1-7" style="zoom:67%;" />

#### 2.2 Creating a New Project

* Click "+Create New Project":

<!-- <img src="../../resources/6-SDKDevelopment/image/createproject1.jpg" alt="7.1.1-7" style="zoom:50%;" /> -->

* `Interpreter` is used to interpret Python programs. Select "Add Interpreter" -> "New" to add a base interpreter.

   <img src="../../resources/6-SDKDevelopment/image/interpreter1.jpg" alt="7.1.1-7" style="zoom:50%;" />

   <img src="../../resources/6-SDKDevelopment/image/interpreter3.jpg" alt="7.1.1-7" style="zoom:40%;" />

* `Location` refers to the location where the Python files are saved. Choose a folder to place your program.

   <img src="../../resources/6-SDKDevelopment/image/location1.jpg" alt="7.1.1-7" style="zoom:40%;" />

* Click "Create", and an example will appear:
   <!-- <img src="../../resources/6-SDKDevelopment/image/createproject2.jpg" alt="7.1.1-7" style="zoom:40%;" /> -->

* Right-click on the option indicated by the red arrow, and create a new Python file.

   <!-- <img src="../../resources/6-SDKDevelopment/image/createproject3.jpg" alt="7.1.1-7" style="zoom:40%;" /> -->

* Type the name of the new file.

   <!-- <img src="../../resources/6-SDKDevelopment/image/createproject4.jpg" alt="7.1.1-7" style="zoom:67%;" /> -->

### **3 Preparation**

* Install pymycobot. Enter the command "pip install pymycobot --upgrade --user" in the terminal (Win+R, type `cmd`).

   ````python
   pip install pymycobot --upgrade --user
   ````

   <img src="../../resources/6-SDKDevelopment/image/pymycobotinstall.jpg" alt="7.1.1-7" style="zoom:80%;" />

* Source code installation. Open the terminal (Win+R, type `cmd`), and then enter the following commands to install.

   ````python
   git clone https://github.com/elephantrobotics/pymycobot.git <your-path>
   #<your-path> is your installation address, do not choose the current default path.
  
   cd <your-path>/pymycobot
   #Enter the pymycobot folder of the downloaded package.
  
   #Run one of the following commands according to your Python version.
   # install
    python2 setup.py install
   # or
    python3 setup.py install
   ````

* Update pymycobot

````bash
pip install pymycobot --upgrade
````

> **Note:**
>
> 1. If there is no red wavy line under the code, it means that pymycobot is successfully installed.
> 2. If there is a red wavy line, please manually download pymycobot from **https://github.com/elephantrobotics/pymycobot** and place it in the Python library.
>
> <img src="../../resources/6-SDKDevelopment/image/pymycobotdownload.jpg" alt="7.1.1-7" style="zoom:33%;" />

## Basic Use of Python

```python
from pymycobot import Mercury

ml = Mercury('/dev/left_arm')
mr = Mercury('/dev/right_arm')

ml.power_on()
mr.power_on()

print(ml.get_angles())
print(mr.get_angles())
```

This code snippet demonstrates how to initialize and power on the left and right arms of the Mercury robot using the pymycobot library. It also retrieves and prints the joint angles of both arms.

---

[← Previous Page](../README.md) | [Next Page →](./6.1.2-ApplicationBasePython.md)
