# 1. Abstract
## 1.1  Introduction
mightyZap Total Manager is software that allows easy management and control of the MightyZap Actuator on various operating systems. 
The features of Total Manager are as follows:
- It allow configure the parameters of all MightyZap actuators with communication capabilities and conduct operational tests
- It enables testing simple motion and observing data that changes over time..
- It supports various protocols to monitor and control the MightyZap's status.
- It can update the firmware of all Smart mightyZap devices.

![[controlfuulshot.png]]

Showing how to run MightyZap Total Manager We recommend the MightyZap Servo Interface Module.
## 1.2 Supported Protocol
- Protocol 1.0
- Modbus-RTU (FC-Only)
- CAN Protocol (BLDC Only)
## 1.3 Supported OS
- Windows : windows 7(32bit) Over
- Mac OS : Big Sur
- Linux : Ubuntu LTD 20.04
	- Tested only on DeskTop & lapTop.
## 1.4 Interface Board
adklfjasdf
aslkdfjaskld



# 2. Software Install
## 2.1 Install on Windows
1. Download the Windows-only package.
	- [Windows Software Download](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
2. Execute the downloaded installation file.
 ![[windows0install.jpg]]
3. Click the Next button to proceed with the installation. 
   ![[windows-install-next.jpg]]

# 3. Menu Description
## 3.1 Screen Description
![[mainView-description.jpg]]
**Main Toolbar**
  A menu that performs Actuator Reset, Restart, Data Undo/Redo, etc.
- **SCAN**
  Connect the software's communication and bring up the window to search for mightyZap.
- **Main Menu**
  Menu to select functions provided by Manager, such as Information, Control, Update, Manager Setting, etc.
- **Actuator List**
  Searched MightyZap names are classified and displayed according to communication speed and protocol.
- **Main contents**
  Main functions provided to the manager are displayed.
- **Actuator Information**
  The model name, firmware version, and communication method of the selected actuator are displayed.
- **Communication Status**
  Indicates communication status such as communication protocol and sending/receiving error.
- **Manager Status**
  Displays the version and language of Manager.
## 3.2 Information
This is a window that displays servo motor information. You can check the model name, motor type, maximum speed, and firmware version of the selected servo motor.
Also, you can check the datasheet and user manual of the servo motor.
![[Information.jpg]]
## 3.3 Control Feature
In the parameter screen, you can set the control value of the MightyZap servo motor or test the operation. Also, you can view the real-time change data as a graph.
![[control-view.jpg]]
It is possible to change parameters such as servo motor ID or Baudrate, or to test motion parameters such as Goal Position in a simple way.
## 3.4 Update Feature
The Update Feature is used to change the firmware version of the servomotor or restore the servomotor that is not being searched. 
![[update-view.jpg]]
# 4. 기본 기능
## 4.1 통신 Port 확인
## 4.2 통신 연결 및 검색
1. 통신 연결을 위해 아래의 그림과 같이 Software를 실행 한 후 우측 상단의 SCAN 버튼을 클합니다.
