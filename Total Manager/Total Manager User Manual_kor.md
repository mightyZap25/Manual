
# 1 Total Manager 시작하기
MightyZap Total Manager 사용자 가이드  

mightyZap Total Manager는 다양한 운영체제에서 MightyZap Actuator를 쉽게 관리 및 제어할 수 있는 Software입니다.
Total Manager에서는 다양한 OS를 제공하고, 사용자 인터페이스를 개선하고 신규 MightyZap 모델을 추가로 지원하는 신규MightyZap Manager 입니다.

이 가이드에서는 Total Manager의 설치와 각 기능의 사용법에 대한 기본 사항을 다룹니다  
>[Total Manager Software Download](https://mightyzap.com/ko/digitalarchive6/?uid=211&mod=document&pageid=1) 페이지에서 다운로드 할 수 있습니다.

## 1.1 개요
mightyZap Total Manager는 다양한 기능을 가진 다목적 Software입니다. MightyZap Actuator의 동작 Test와 Parameter 설정 및 동작 상태 Monitoring과 Firmware Update를 기본적으로 제공합니다.  
또한 모델에 따른 특수 기능을 설정 및 테스트 할 수도 있습니다. 
>특수 기능 설정 및 테스트 내용은 각 모델의 매뉴얼을 참조하시기 바랍니다.

![[total_image.png]]

## 1.2 사용 환경
MightyZap Actuator는 Half Duplex TTL, RS485, CAN 통신을 사용합니다. PC와의 통신을 위한 컨버터를 사용해야 Actuator와의 통신이 가능합니다.  
당사에서는 MightyZap Actuator를 위한 USB Interface Board를 판매하고 있습니다. 당사의 Interface Board를 사용할 경우 손쉽게 MightyZap을 PC와 연결할 수 있습니다.  
시중의 Convertor를 구매하여 사용하실 수 있지만, 안전성을 위하여 가급적 당사의 Interface Board를 사용하여 주시기 바랍나다.

> <font color="#ff0000">주의 사항</font><br>
> PC와 Interface Board와의 연결에 사용하는 Cable중 통신이 되지않는 충전 전용 Cable을 사용하여 통신이 연결되지 않는 경우가 있습니다. 반드시 확인하시고 사용하여 주시기 바랍니다.

## 1.3 Feature
### 1.3.1 Information
연결된 MightyZap Actuator의 Model명, Stroke, Rate Load, Firmware Version 등 Actuator와 관련된 기본 정보를 표시합니다.   
Software를 실행하였을 경우 제일 처음에 나타나는 화면입니다.
![[Information.jpg]]
### 1.3.2 Parameter
MightyZap Actuator를  제어하거나 Paramter를 변경 및  Monitoring을 할 수 있습니다.   
연결된 여러개의 서보모터 중 선택하여 개별적으로 제어할 수 있으며, Paramter의 Type에 따라 Non-voltatile Memory와 Volatile Memoty 화면으로 나누어져 있습니다.    
사용 모델에 따라 Parameter의 구성이 달라지며, 화면의 크기에 따라 화면 구성이 다이나믹하게 변하게 됩니다.   
![[control-view.jpg]]
### 1.3.3 update
MightyZap Actuator의 Firmware를 Update할 때 사용합니다. 당사의 Webpage에서 해당 모델에 맞는 업데이트 파일을 다운로드 받으신 후 업데이트를 진행 하실 수 있습니다.  
또한, Update Fail 및 사용자의 실수로 인해 서보모터가 검색이 되지 않을 경우 Firmware를 검사 및 복구 하실 수도 있습니다.  
![[update-view.jpg]]*caption*
# 2 Total Manager 다운로드 및 설치
이 튜토리얼에서는 Windows. Mac 또는 Linux 컴퓨터에서 Total Manager를 다운로드하고 설치하는 방법을 보여줍니다.
## 2.1 요구사항
- Windows : windows 7(32bit) 이상  
- Mac OS : Big Sur 이상 64bit
- Linux : Ubuntu LTD 20.04 64bit

## 2.2 Install
### 2.2.1 Windows
Windows 컴퓨터에서 MightyZap Total Manager를 설치하려면 사용중인 Windows의 
OS 버전을 확인하신 후 버전에 맞게 다운로드하여 주시기 바랍니다.  
<font color="#4f81bd">OS Version 확인 방법</font>
![[windows_version_check.jpg]]


다운로드한 파일을 실행하여, 설치 가이드의 지침에 따라 설치하시면 됩니다.  
설치에는 몇 분 정도 걸릴 수 있습니다.
![[window_install.jpg]]
이제 Window에서 MightyZap Total Manager를 사용하실 수 있습니다.  

### 2.2.2 Linux
Linux 전용 패키지를 다운로드 합니다.
	- [Linux Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
Debian,/Ubuntu 기반 배포용 Total Manager를 설치하기 위해서는 다음과 같은 Command Line을 통해 .deb 패키지(64bit)를 다운로드하고 설치하는 것입니다.
>sudo apt install ./[file].deb
> - If you're on an older Linux distribution, you will need to run this instead:
> - sudo dpkg -i [file].deb
> - sudo apt-get install -f # Install dependencies

### 2.2.3 Mac OS

## 2.3 화면 구성
화면 구성은 크게 4가지로  Header 부분과 Side bar, Contents, Fotter로 구성되어있다.  
![[mainView-description.jpg]]
**1)uMain Toolbar**    
  Actuator의 Reset, Restart, Data Undo/Redo 등을 수행하는 매뉴
**2) SCAN**  
  Software의 통신을 연결하고 mightyZap을 검색하는 창을 불러 옵니다.
**3) Main Menu**  
  Information, control, Update, Manager Setting 등 Manager에서 제공하는 기능을 선택하는 메뉴
**4) Actuator List**  
  검색된 MightyZap의 이름이 통신 속도와 Protocol에 따라 분류되어 표시
**5) Main contents**  
  매니저에 제공하는 Main 기능을 표시합니다.
**6) Actuator Information**  
  선택된 Actuator의 모델명, Firmware Version, 통신 방식 등이 표기 됩니다.
**7) 통신 상태**  
  통신 Protocol 및 송수신 Error 등 통신 상태를 나타냅니다.
**8) Manager Status**  
  Manager 의 버전 및 Language 를 표시합니다.
## 2.4 USB Interface Board 
Total Manager와 MightyZap Actuator와의 통신을 위하여 Serail convertor 가 필요합니다.  
해당 설명은 당사의 USB Interface Board를 기준으로 설명이 되어있습니다.  
먼저 USB Cable을 이용하여 PC와 연결하여 주시기 바랍니다.   
> <font color="#ff0000">주의사항 </font>     
> <font color="#ff0000">충전 전용 케이블이 아닌 통신이 가능한 케이블을 사용하여 주셔야합니다.</font>

### 2.4.1 Windows
USB Interface Board Driver를 다운로드 합니다.
	-  [USB Interface Board Window Driver]
다운로드한 파일을 실행하고 가이드에 따라 드라이버를 설치합니다.
**- USB Interface board - 02** (CH340x)
![[ch340x_win_install.jpg]]
  
**- USB Interface Board - 03** (FTDI)
![[ftdi_win_install.png]]

USB Interface Board를 PC와 연결합니다.
[시스템]-[장치관리자]-[port]에서 Serial Port가 정상적으로 연결되었는지 확인합니다.  
정장적으로 연결되어 있을 경우 이미지에서와 같이 새로운 com port가 추가되는것을 확인할 수 있습니다.
![[serialPort_check_win.jpg]]
### 2.4.2 Linux[ubuntu/Demian]
#### Driver 설치
##### 1) CH341 Driver 
CH341 driver는 USB-02 Model에서 만 사용됩니다. 
CH340, CH341 의 시리얼 드라이버는 Linux 커널 버전 2.6.24부터 내장되어 있으며, 해당 위치는 drivers/usb/serial/ch341.c입니다. 다만 드라이버를 최신 상태로 유지 하기 원하실 경우 아래의 방법을 사용하기 바랍니다.
 - 아래의 사이트에서 Linux용 드라이버를 다운로드 받으시기 바랍니다.
   [LINUX용 CH341 Driver Donwload(ZIP)](https://www.wch.cn/downloads/CH341SER_LINUX_ZIP.html)  
 - 다운로드한 파일의 압축을 풉니다.
 - 터미널 창을 열고 다운로드한 디렉토리로 이동을 합니다.
 - 다음의 명령들을 입력합니다
   >$ make clean
   >$ make
   >$ sudo make load  
   
 - 설치된 드라이버를 확인하기 위해 USB-02를 PC와 연결한 후 다음의 명령을 입력합니다.  
   정상적으로 설치가 되었다면 "ch34x"로 표시되어야 합니다.
   >$ sudo dmesg | grep ch34  
   >[   xxx] usbcore: registered new interface driver ch341
   >[   xxx] usbserial: USB Serial support registered for ch341-uart
   >[   xxx] ch341 1-6.4.3:1.0: ch341-uart converter detected
   >[   xxx] usb 1-6.4.3: ch341-uart converter now attached to ttyUSB1
##### 2) FTDI Driver
FTDI Driver는 USB-02를 제외한 모든 모델에서 사용됩니다.
FTDI VCP 드라이버는 Linux  커널에 내장되어 있으므로 이 드라이버는 있습니다. 모든 FTDI 장치에 VCP 드라이버 지원이 있는지 홗인하기 위해 FTDI는 Linux  시스템에 최신 커널 릴리즈를 설치할 것을 권장합니다. Linux 에서는 VCP 드라이버가 /dev/ttyUSBx로 표시됩니다.
Comport를 확인하는 방법 :
- USB Interface board를 PC와 Cable로 연결한다.
- 터미널 창을 열고 다음을 입력하면 다음과 같이 출력이 나타납니다.
  >$ dmesg|grep FTDI
  >  [   xxx] USB Serial support registered for FTDI USB Serial Device 
  >  [   xxx] ftdi_sio 9-1:1.0: FTDI USB Serial Device converter detected 
  >  [   xxx] usb 9-1: FTDI USB Serial Device converter now attached to ttyUSB0 
  >  [   xxx] ftdi_sio: v1.6.0:USB FTDI Serial Converters Driver
  
#### Serial Port 권한 얻기
우분투는 기본적으로  root 사용자가 아닌 일반 사용자로 로그인하도록 하기 때문에 Serial Port와 같은 시스템 장치를 다루기 위해서는 권한 설정을 해야 합니다.   
먼저 연결된 Port 명을 확인하기 위해 아래의 명령을 입력합니다.
>$ dmesg|grep tty
>[   xxx] printk: console [tty0] enabled
>[   xxx] usb 1-6.1.4: FTDI USB Serial Device converter now attached to ttyUSB0
>[   xxx] ftdi_sio ttyUSB0: FTDI USB Serial Device converter now disconnected from ttyUSB0
>[   xxx] usb 1-6.1.4: FTDI USB Serial Device converter now attached to ttyUSB0

"ls -l" 명령을 이용하여 확인된 Serial Port를 이용하여 사용 그룹을 확인합니다.
>$ ls -l /dev/ttyUSB0
>   crw-rw---- 1 root dialout 188,  0 11월  1 10:49 /dev/ttyUSB0

"id Gn" 명령을 통해 현재 로그인 중인 사용자가 속한 그룹을 확인합니다.
>$ id -Gn
>user adm cdrom sudo dip plugdev

현재 로그인한 사용자에서 dialout 그룹이 포함되어 있지 않기 때문에, 현재 사용자에게 dialout 그룹을 추가해 줍니다.
>$ sudo adduser $USER dialout
>[sudo] password for user.
>Adding user 'user' to group 'dialout' ...
>Adding user user to group dialout
>Done

그룹에 추가 한 후에는 반드시 로그아웃 후 로그인 해야 변경 사항이 적용 됩니다.
### 2.4.3 Mac OS
USB Interface Board Driver를 다운로드 합니다.  
	-  [USB Interface Board Window Driver]  
다운로드한 파일을 실행하고 가이드에 따라 드라이버를 설치합니다.  
	[이미지 ]  
USB Interface Board를 PC와 연결합니다.  
[시스템 정보]-[Hardware]-[USB]에서 Serial Port가 정상적으로 연결되었는지 확인합니다.    
정장적으로 연결되어 있을 경우 이미지에서와 같이 새로운 com port가 추가되는것을 확인할 수 있습니다.  
[이미지]  
# 3 Total Manager Description
## 3.1 통신 연결 및 검색
아래의 이미지와 같이 프로그램을 실행 한 후 상단 매뉴바에서 Scan 버튼을 누르면 Actuator Scan을 위한 팝업 창이 활성화 됩니다.   
![[Pasted image 20231027100657.png]]
### 3.1.1 SCAN 화면 구성
Actuaotor Scan 팝업 창의 화면 구성은 아래와 같습니다.  
![[Pasted image 20231102175315.png]]
- **Serial Port**  : USB Interface Board의 Serial Port
- **Protocol** : 통신 프로토콜 설정, Actutator Model에 따라 다르며 Scan시 중복 선택 가능
- **Baudrate Select** :  통신 속도 설정 (default 57600bps) Scan시 중복 선택 가능
- **Scan 결과 창** : SCAN 진행 상황과 결과를 출력한다.
- **SCAN, CLOSE** : SCAN 실행 및 창 닫기 버튼
### 3.1.2 통신 설정
##### 1. Port 선택
위 [[#2.4 USB Interface Board]] 의 설명을 참조하시어 Serial Port 명을 확인 하신 후 진행하시기 바랍니다.  연결된 Serial Port와 동일한 Port를 선택한 후 OPEN 버튼을 클릭하여 Serial Port를 연결합니다.  ![[Pasted image 20231102174400.png]]
Serial Port 를 Open하면 Option 항목이 활성화 됩니다.  
모든 옵션은 중복으로 선택할 수 있으며 검색 시 순차적으로 진행이 됩니다.  
All 버튼을 누르게 되면 모든 선택하거나 모두 선택 해지를 하게 됩니다.
   ![[yrdy-2023-07-25_10.39.gif]]
  
다음은 모델에 따른 기본 설정 값에 대한 예시 입니다.  
 
|   예시 모델         |   Protocol(dafault)                 |   Baudrate (dafault)          |
|:------------------|:----------------------------|:---------------------|
|   **Mini L12/12Lf**   | Own Protocol                |             57600pbs |
|   **Mini 17Lf**       | Modbus Protocol             |             57600pbs |  

### 3.1.3 Actuator 검색
 SCAN 버튼을 누르게 되면 선택한 옵션에 따라 차례로 검색을 시작하여 해당 결과를 표시합니다.
 원하는 Actuator 가 모두 검색 되었을 경우, 완료를 기다리지 않고 STOP 버튼을 click하면 검색을 종료하면 됩니다.  
![[Pasted image 20231027100637.png]]
 검색이 완료되었으면 Close 버튼을 click하여 Popup 창을 닫습니다.
## 3.2 Information
MightyZap Actuator의 Model명, Rated Load, Stroke, firmware Version등 관련된 정보를 표시하는 페이지 입니다.  
Manager가 실행이 되면 처음 표시하는 창이  창이며, 아래의 이미지와 같이 사이드 바 매뉴의 첫번째 아이콘을 클릭하면 해당 페이지로 이동합니다.
![[InformationMenu.png]]
### 3.2.1 서보모터 List 확인
아래의 그림과 같이 매니저에 왼쪽에는 검색된 서보모터가 Display 됩니다.  
Actuator List는 Baudrate와 Protocol에 따라 분류되어 표시 되며,  Baudrate 별로 접거나 펼 수 있다.  
![[Pasted image 20231027102021.png]]

### 3.2.2 정보 확인
Actuator List를 선택하면 해당 Actuator의 정보가 표시되며, 이중 중요한 일부 정보가 Manager의 하단 Footer에 표시됩니다.
![[Pasted image 20231027103448.png]]
Footer에 표시된 정보는 information Page가 아닌 다른 Page에서도 볼 수 있습니다. 
## 3.3 Parameter
MightyZap Actuator를 설정 및 간단한 동작 테스트를 하고, 동작 상태를 모니터링하는 페이지 입니다.  
Menu 선택 창에서 아래의 그림과 같은 아이콘을 클릭하면 해당 페이지로 이동합니다.
![[Pasted image 20231027103618.png]]
사용자 환경에 맞게 Stroke, ID, Baudrate 등을 설정하고 간단한 동작 테스트를 진행할 수 있습니다.  
각 Parameter에 대한 설명은 해당 모델의 사용자 매뉴얼에서 Parameter 설명을 참조하시기 바랍니다.
### 3.3.1 화면 구성
Parameter 페이지의 구성은 Non-Volatile Memory 영역과 Volatile Memory 영역으로 나뉩니다.
Non-volatile Meomory는 비 휘발성 메모리 영역의 Parameter로 수정 및 저장된 Data가 내부 Falsh Memeory에 저장이 되며, 모터의 전원이 꺼지게 되어도 지워지지 않고 저장되어있습니다.  
Volatile Memory는 휘발성 메모리 영역으로 내부 Ram에 저장이 되며, 전원이 꺼지기 전까지는 해당 Data를 저장하고 있지만, 전원이 꺼지게 되면 해당 Data는 초기화 됩니다.  
Parameter 영역은 매니저의 크기를 줄일 경우, 주로 사용되어지는 Volatile-Memeory 영역이 상단으로 이동합니다.   
![[Pasted image 20231027104017.png]]

**Tooltip 기능**
각 Paremater 이름의 옆에는 (?)를 한 아이콘이 있습니다. 해당 아이콘에  mouse를 가져가 대면 해당 파라메터에 대한 간단한 설명이 표시됩니다.  
![[Pasted image 20231027104205.png]]
### 3.3.2 Parameter Control
- **Slide Control** : <font color="#4f81bd">Non-volatile Memory</font>  
  Non-Volatile Memeory의 가장 일반적인 Data 변경 방식으로 Slide bar의 Drag 또는 TextBox에 직접 Data를 입력하는 방법으로 Data를 변경 합니다.   
  ![[Pasted image 20231027105414.png]]
  값을 변경할 경우 오른쪽의 TextBox의 값이 푸른색으로 변경되며, 변경한 data를 저장하기 위해서는 S  버튼을 클릭해야 합니다.   ![[Pasted image 20231027105306.png]]
  S 버튼을 클릭하지 않고 다른 Parameter를 변경하려 할 경우 Data는 원래 상태로 복구 되며 TextBox의 font가 다시 흰색으로 변경됩니다.  
  
- **Slide Control** : <font color="#4f81bd">Volatile Memory</font>  
  Volatile Memory에서의 Slide Control 방식은 Non-Volatile Memory 방식과 유사하지만, S 버튼이 없으며, Slide bar를 Drag할 경우 변경된 Data가 즉시 적용됩니다.  
  ![[Pasted image 20231027110327.png]]
  또한 TextBox를 통해 Data를 입력할 경우 Data를 변경한 후 Enter key를 입력하면 변경된 Data가 즉시 적용됩니다.
  또한 Data가 변경되도 TextBoxd의 Font는 푸른색으로 변경되지 않습니다.
  ![[Pasted image 20231027110455.png]]  
  ><font color="#4f81bd">Tip</font>  
  >Goal Position TextBox를 클릭한 후 다음과 같이 키보드 키로 제어가 가능합니다.  
  > 	'a' : 최소 stroke로 이동
  > 	's' : stroke 중간 위치로 이동
  > 	'd' : 최대 Stroke로 이동  
- **Check Control Box** : <font color="#4f81bd">Non-volatile Memory</font>   
  Check Control은 check 기능을 이용하여 Data를 변경 가능하며, 이때 Textbox는 Read Only 상태로 Data값과 상태만을 확인할 수 있습니다.  
  ![[Pasted image 20231027110812.png]]
  checkbox는 모두 선택, 모두 해제, 부분 선택 모두 가능하며,선택 값이 변경되었을 경우 TestBox의 font가 푸른색으로 변경됩니다.  
  수정한 값을 적용하기 위해서는 S 버튼을 눌러 수정된 값을 저장해야 합니다.  
  버튼을 클릭하지 않고 다른 Parameter를 변경하려 할 경우 Data는 원래 상태로 복구 되며 TextBox의 font가 다시 흰색으로 변경됩니다.   
- **Select Control box** : <font color="#4f81bd">Non-volatile Memory</font>   
   Select Control box는 Select 기능을 이용하여 Data를 변경 가능하며, 이때 Textbox는 Read Only 상태로 Data값과 상태만을 확인할 수 있습니다.
  select 값이 변경되었을 경우 TestBox의 font가 푸른색으로 변경되며, 
  수정한 값을 적용하기 위해서는 S 버튼을 눌러 수정된 값을 저장해야 합니다.
  ![[Pasted image 20231027111059.png]]  
  버튼을 클릭하지 않고 다른 Parameter를 변경하려 할 경우 Data는 원래 상태로 복구 되며 TextBox의 font가 다시 흰색으로 변경됩니다.  
- **Select box** : <font color="#4f81bd">Volatile Memory</font>   
  Volatile Memory 의 Select Control Box에는 TextBox가 존재하지 않습니다.
  Select 기능을 이용하여 선택된 Data를 즉시 적용합니다.
  ![[Pasted image 20231027111510.png]]
- **Button Control Box** : <font color="#4f81bd">Volatile Memory</font>   
   Button control Box 기능은 Volatilte Memory에 만 있는 기능으로 Motor의 동작을 정지하기 위해 사용됩니다.
   아래의 그림과 같이 Button은 활성화 비활성화에 따라 2가지의 이미지를 가지고 있으며, 해당 Parameter에 대한 자세한 설명은 해당 제품의 사용자 매뉴얼을 참조하여 주시기 바랍니다.
   ![[Pasted image 20231027111843.png]]
### 3.3.3 Monitoring
Monitoring 기능은 MightyZap Actuator의 현재 위치, 모터 입력 값, 전류 등을 실시간으로 확인하는 기능을 가지고 있습니다.  
Parameter 항목은 Model에 따라 다르게 표시되며, Check box를 통해 하나의 Paramter만 선택하실 수 있습니다.  
![[Pasted image 20231027113502.png]]
Monitoring 기능은 아래와 같이 구성 되어있습니다.
- **Data 범위**
  Data 표현 범위는 선택된 Paramter의 표현 범위에 맞게 변경이 됩니다.
- **Sample 표현 갯 수**
  최대 Display되는 Sample 갯 수는 200개이며 이전 Data는 확인할 수 없습니다. Sample Counter의 최대 표현 수는 899이며 이보다 클 경우 0으로 리셋이 됩니다.
- **Interval**  
  Interval은 Data Sample 당 읽어오는 시간 간격을 의미하며 약 50ms 간격으로 동작 합니다.     
- **Hover 기능**
  마우스를 그래프 위에 놓으면 해당 위치의 데이터 값과 Sample Counter 값을 표기합니다.
## 3.4 Update    
펌웨어를 업데이트 하는 페이지 입니다.  Firmware의 버전은 최신 버전을 유지하는 것을 추천 드립니다. 다만 수정된 펌웨어를 적용하기 전에  변경 사항이 사용자의 Apllication과 적합한지 테스트 하신 후에 적용하시기 바랍니다.   
펌웨어 파일은 당사의 homepage에서 다운로드 받으시기 바랍니다.  
www.mightyzap.com  
### 3.4.1 화면 구성    
Update Page는 이미지와 같이 펌웨어 업데이트, Actuator Recovery 영역으로 되어있으며, 각각의 실행은 상단 header의 메뉴에서 해당 아이콘을 선택하여 실행할 수 있습니다.  
![[Pasted image 20231027113746.png]]
### 3.4.2 Firmware Update   
**Actuator 연결**  
업데이트를 진행할 서보 모터를 연결하고 SCAN 을 합니다.  
><font color="red">주의 사항  </font>  
>펌웨어 업데이트 시에는 업데이트를 진행할 actuator 하나만 연결하고 SCAN 작업을 진행하여 Actuator List에 하나의 actuator만 남아 있어야 합니다.  하나 이상의 actuator 가 연결 된 상태에서 업데이트를 진행하면 업데이트가 비정상적으로 진행되어 실패하게 되고 해당  actuator 는 동작이 되지 않게 됩니다.  
  
**업데이트 파일 선택**  
firmware update를 진행 할 경우 그림과 같이 Select file 버튼을 눌러 다운로드 받은 업데이트 파일을 선택해야 합니다.    
![[Pasted image 20231027114211.png]]
><font color="#ff0000">주의 사항  </font>
>이때 다른 모델의 firmware file 을 선택하지 않게 조심해야 합니다. Actuator List에 나와있는 Model 명과 uipdate file의 이름이 동일한지 확인해야 합니다.

**업데이트**  
모든 사항이 준비가 다 되었으면 상단 메뉴바에서 Update 아이콘을 클릭합니다.   
![[Pasted image 20231027114323.png]]
이때 둘 이상의 actuator 가 연결되었을 경우 다음과 같은 경고창이 나타나고 SCAN  작업을 다시 합니다.  
![[Pasted image 20231027125842.png]]
업데이트를 위해서는 서보모터가 재 시작 해야하는데 정상적으로 통신이 이루어지지 않는 경우 아래의 그림과 같이 서보모터의 커넥터를 다시 연결하라는 메세지가 나타납니다.
![[Pasted image 20231027125533.png]]

**업데이트 완료**
업데이트가 진행되면 그림과 같이 prograss bar가 진행이 됩니다. 100%까지 완료되면 update 완료 메세지가 나타납니다.    
![[Pasted image 20231027134349.png]]
필요에 따라 reset이나 Factory Rest을 추가적으로 진행하시면 됩니다.  
  
**펌웨어 업데이트 실패**  
### 3.4.3 Recovery  
Firmware 가 업데이트 실패 또는 SCAN을 통해 서보 모터를 검색하지 못할 경우 Recovery를 진행합니다. 문제가 발생한 Actuator 만을 연결한 후 상단 매뉴의 Recovery 아이콘을 클릭합니다.  
![[Pasted image 20231027130532.png]]

Recovery 진행 사항은 각 단계마다 이미지 또는  Text로 그 단계를 표시합니다.
![[Pasted image 20231027130612.png]]
 - **Actuator Search**  
   검색 단계에서는 각 모든 Baudrate와 Protocol로 서보모터를 검색합니다. 이때 서보모터가 검색이 될 경우 Recovery를 완료하고 서보머터를 Servo List에 자동으로 추가합니다,.
   ![[Pasted image 20231027131044.png]]

- **Restart**   
   검색이 되지 않았을 경우 아래의 팝업 창이 나타나면서 커넥터를 다시 연결하라는 문구가 나타납니다. Close 버튼을 누르면 업데이트 창에 "Reconnect Actuator" 문구가 나타납니다. 이때 서보모터의 연결된 커넥터를 재거 한 후 다시 연결하여 주시기 바랍니다.
  ![[Pasted image 20231027133454.png]]
- **Check Bootloader &&Update Firmware**  
  커넥터를 다시 연결하면 Bootloader를 확인 한 후 복구할 Actuator의 Update 파일을 선택하라는 팝업 창이 나타납니다. Select 버튼을 누른 후 Update대와 같이 업데이트 파일을 선택하시면  업데이트가 진행이 됩니다.
  ![[Pasted image 20231027133800.png]]
- **Calibration**  
  Recovery는 Update와는 다르게 Update 후 Calibration 작업을 진행합니다. Calibration 단계에서는 서보모터의 Stroke가 수축 및 확장 작업을 진행하며 완료 될 때 까지 기다라시면 됩니다.  
- **Done**
  완료가 되면 업데이트 완료 팝업이 나타나고, SCAN 창이 활성화 됩니다. 
  ![[Pasted image 20231027134732.png]]
### 3.4.4 Factory Reset   
Actuator의  상태를 공장 출하 시의 초기 상태로 돌리고, 위치 값을 결정하는 Potentiometer의 Calibration을 진행합니다.  
><font color="#ff0000">주의사항</font>  
>Factroy Reset 중에 Actuator가 Calibration을 위해 최대./최소로 위치이동을 합니다. 정상적인 Calibration을 위해 장치에 연결하지 않고 무부하에 최대 동작거리를 유지할 수 있는 공간에서 진행해 주시기 바랍니다.

##### 1. ICON
Factory Reset은 Update Page에 들어오면 상단 매뉴바에 추가 되어있는 것을 확인할 수 있습니다.   
해당 아이콘을 클릭하면 Factory Reset 을 하기 위한 팝업 창이 활성화 됩니다.
![[Pasted image 20231027134845.png]]
##### 2. 화면 구성
Factory Reset을 선택하면 팝업 창이 나타납니다. 팜업창에는 Factory Reset 관련 Option 선택창과 Text Area가 나타나고 하단에 Factory Reset 을 위한 버튼이 존재합니다.  
![[Pasted image 20231027135429.png]]
##### 3. Options
Factory Reset에 대한 Option은 2가지로 ID Remind와 Baudrate Reminde 입니다. 그 외의 다른 Parameter들은 모두 초기화 됩니다.  
일반적인 Reset 에서는 초기화 되지 않는 Protocol, Min/Max Position Calibration이 초기화 되고, Potentiometer의 Calibration을 실행하면서 해당 내부 Parameter도 수정이 됩니다.  
Factopry Reset 후에도 유지하고 싶은 Option을 선택하시면 됩니다.  
##### 4. Factory Reset 
하단의 Factory Reset 버튼을 클릭하면, Factory Reset을 실행합니다. 실행 중 진행되는 사항을 Option 선택 아래의 Text Area 창에 표시합니다. 
![[Pasted image 20231027135548.png]]
Factory Reset 진행이 되면서 Actuator가 몇 번의 시스템 재 시작을 하면서 LED가 깜빡입니다. 또한 Potenmtiometer Calibration 시에는 Actuator가 최대로 확장 및 수축 행동을 하면서 Calibration 을 진행합니다.  
최종적으로 Factory Reset이 완료되면 하단의 Close 버튼이 활성화 되면서 Parameter 창으로 이동하여 reset된 Data를 보여줍니다.
![[Pasted image 20231027135707.png]]

> <font color="#ff0000">주의 사항</font>  
> Calibration 을 하기 앞서, 정확한 Calibration 작업을 위해 Actuator 에 연결되어있는 모든 기구물을 제거하여, 무 부하 상태에서 Full Stroke 구간에 걸쳐 기구 간섭이 없도록 합니다.



// restart , reset 설명 추가