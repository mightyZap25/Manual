
# Total Manager 시작하기
MightyZap Total Manager 사용자 가이드  
<p align="right">LAST REVISION: 2023.07.22</p>

mightyZap Total Manager는 다양한 운영!체제에서 MightyZap Actuator를 쉽게 관리 및 제어할 수 있는 Software입니다.
Total Manager에서는 다양한 OS를 제공하고, 사용자 인터페이스를 개선하고 신규 MightyZap 모델을 추가로 지원하는 신규MightyZap Manager 입니다.

이 가이드에서는 Total Manager의 설치와 각 기능의 사용법에 대한 기본 사항을 다룹니다  
>[Total Manager Software Download](https://mightyzap.com/ko/digitalarchive6/?uid=211&mod=document&pageid=1) 페이지에서 다운로드 할 수 있습니다.

## 개요
mightyZap Total Manager는 다양한 기능을 가진 다목적 Software입니다. MightyZap Actuator의 동작 Test와 Parameter 설정 및 동작 상태 Monitoring과 Firmware Update를 기본적으로 제공합니다.  
또한 모델에 따른 특수 기능을 설정 및 테스트 할 수도 있습니다. 
>특수 기능 설정 및 테스트 내용은 각 모델의 매뉴얼을 참조하시기 바랍니다.

![[total_image.png]]

## 사용 환경
MightyZap Actuator는 Half Duplex TTL, RS485, CAN 통신을 사용합니다. PC와의 통신을 위한 컨버터를 사용해야 Actuator와의 통신이 가능합니다.  
당사에서는 MightyZap Actuator를 위한 USB Interface Board를 판매하고 있습니다. 당사의 Interface Board를 사용할 경우 손쉽게 MightyZap을 PC와 연결할 수 있습니다.  
시중의 Convertor를 구매하여 사용하실 수 있지만, 안전성을 위하여 가급적 당사의 Interface Board를 사용하여 주시기 바랍나다.

> <font color="#ff0000">주의 사항</font><br>
> PC와 Interface Board와의 연결에 사용하는 Cable중 통신이 되지않는 충전 전용 Cable을 사용하여 통신이 연결되지 않는 경우가 있습니다. 반드시 확인하시고 사용하여 주시기 바랍니다.

## Feature
### Information
연결된 MightyZap Actuator의 Model명, Stroke, Rate Load, Firmware Version 등 Actuator와 관련된 기본 정보를 표시합니다.   
Software를 실행하였을 경우 제일 처음에 나타나는 화면입니다.
![[Information.jpg]]
### Parameter
MightyZap Actuator를  제어하거나 Paramter를 변경 및  Monitoring을 할 수 있습니다.   
연결된 여러개의 서보모터 중 선택하여 개별적으로 제어할 수 있으며, Paramter의 Type에 따라 Non-voltatile Memory와 Volatile Memoty 화면으로 나누어져 있습니다.    
사용 모델에 따라 Parameter의 구성이 달라지며, 화면의 크기에 따라 화면 구성이 다이나믹하게 변하게 됩니다.   
![[control-view.jpg]]
### update
MightyZap Actuator의 Firmware를 Update할 때 사용합니다. 당사의 Webpage에서 해당 모델에 맞는 업데이트 파일을 다운로드 받으신 후 업데이트를 진행 하실 수 있습니다.  
또한, Update Fail 및 사용자의 실수로 인해 서보모터가 검색이 되지 않을 경우 Firmware를 검사 및 복구 하실 수도 있습니다.  
![[update-view.jpg]]*caption*
# Total Manager 다운로드 및 설치
이 튜토리얼에서는 Windows. Mac 또는 Linux 컴퓨터에서 Total Manager를 다운로드하고 설치하는 방법을 보여줍니다.
## 요구사항
- Windows : windows 7(32bit) 이상  
- Mac OS : Big Sur 이상 64bit
- Linux : Ubuntu LTD 20.04 64bit

## Install
### Windows
Windows 컴퓨터에서 MightyZap Total Manager를 설치하려면 사용중인 Windows의 
OS 버전을 확인하신 후 버전에 맞게 다운로드하여 주시기 바랍니다.  
<font color="#4f81bd">OS Version 확인 방법</font>
![[windows_version_check.jpg]]


다운로드한 파일을 실행하여, 설치 가이드의 지침에 따라 설치하시면 됩니다.  
설치에는 몇 분 정도 걸릴 수 있습니다.
![[window_install.jpg]]
이제 Window에서 MightyZap Total Manager를 사용하실 수 있습니다.  


### Mac OS
Mac OS 전용 패키지를 다운도르 합니다.  
[MAC OS Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
macOS에서 MightyZap Total Manager를 설치하려면 다운로드한 파일을 어플리케이션 폴더에 복사하기만 하면 됩니다.  
![[Pasted image 20230721150751.png]]
이제 macOS에서 MightyZap Total Manager를 사용하실 수 있습니다.  
### Linux
Linux 전용 패키지를 다운도르 합니다.
	- [Linux Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
terminal  창을 열고 다음과 같이 설치를 합니다.
Ubnuntu (>=22.04)
>sudo dpkg total-manager

## 화면 구성
화면 구성은 크게 4가지로  Header 부분과 Side bar, Contents, Fotter로 구성되어있다.  
![[mainView-description.jpg]]
- **Main Toolbar**    
  Actuator의 Reset, Restart, Data Undo/Redo 등을 수행하는 매뉴
- **SCAN**  
  Software의 통신을 연결하고 mightyZap을 검색하는 창을 불러 옵니다.
- **Main Menu**  
  Information, control, Update, Manager Setting 등 Manager에서 제공하는 기능을 선택하는 메뉴
- **Actuator List**  
  검색된 MightyZap의 이름이 통신 속도와 Protocol에 따라 분류되어 표시
- **Main contents**  
  매니저에 제공하는 Main 기능을 표시합니다.
- **Actuator Information**  
  선택된 Actuator의 모델명, Firmware Version, 통신 방식 등이 표기 됩니다.
- **통신 상태**  
  통신 Protocol 및 송수신 Error 등 통신 상태를 나타냅니다.
- **Manager Status**  
  Manager 의 버전 및 Language 를 표시합니다.
## USB Interface Board 
Total Manager와 MightyZap Actuator와의 통신을 위하여 Serail convertor 가 필요합니다.  
해당 설명은 당사의 USB Interface Board를 기준으로 설명이 되어있습니다.  
먼저 USB Cable을 이용하여 PC와 연결하여 주시기 바랍니다.   
> <font color="#ff0000">주의사항 </font>     
> <font color="#ff0000">충전 전용 케이블이 아닌 통신이 가능한 케이블을 사용하여 주셔야합니다.</font>

### Windows
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
### mac OS
USB Interface Board Driver를 다운로드 합니다.  
	-  [USB Interface Board Window Driver]  
다운로드한 파일을 실행하고 가이드에 따라 드라이버를 설치합니다.  
	[이미지 ]  
USB Interface Board를 PC와 연결합니다.  
[시스템 정보]-[Hardware]-[USB]에서 Serial Port가 정상적으로 연결되었는지 확인합니다.    
정장적으로 연결되어 있을 경우 이미지에서와 같이 새로운 com port가 추가되는것을 확인할 수 있습니다.  
[이미지]  

### Linux[ubuntu 22.04]
Manual installation is not necessary, all FTDI devices are now supported in Ubuntu 11.10, kernel 3.0.0-19.  
만양ㄱ
USB Interface Board Driver를 다운로드 합니다.    
  [USB Interface Board Window Driver]   
다운로드한 파일을 실행하고 가이드에 따라 드라이버를 설치합니다.    
  [이미지 ]  
USB Interface Board를 PC와 연결합니다.    
[시스템 정보]-[Hardware]-[USB]에서 Serial Port가 정상적으로 연결되었는지 확인합니다.  
정장적으로 연결되어 있을 경우 이미지에서와 같이 새로운 com port가 추가되는것을 확인할 수 있습니다.    
[이미지]  
터미널 창을 열고 아래와 같이 port 권한 설정을 사용자 계정에 추가해 주어야  Serial Port의 사용이 가능하게 됩니다.     
- USB Interface Board 03 - FTDI Install Guide  
   - [FTDI Install Fuide Link](https://ftdichip.com/document/installation-guides/https://ftdichip.com/document/installation-guides/)  

# Total Manager Description
## 통신 연결 및 검색
아래의 이미지와같이 프로그램을 실행 한 후 상단 매뉴바에서 Scan 버튼을 누르면 Actuator Scan을 위한 팝업창이 활성화 됩니다.  
![[scanbutton.png]]
### 화면 구성
Actuaotor Scan 팝업창이 나오면  위의 OS별 Serial Port 확인을 참조하여 연결된 Comport를 확인한 후 Open 버튼을 클릭합니다.    
정상적으로 comport 연결 되었을 경우 오른쪽 그림과 같이 비활성화 되었던 창이 활성화가 되며 Actutor를 검색 할 준비가 됩니다.
![[scanning.png]]
Scan Actuator 창은 아래와 같이 구성되어있습니다.
**Scan Actuator 화면 구성**
- Serial Port Select (default :Won Protocl)
- Baudrate Select (default :57600bps)
- Scan 결과 창
- Scan, close 버튼 창
### 통신 설정
 Serial Port 를 Open 한 후 Protocol과 Baudrate를 선택한 후 검색을 진행 해야 합니다.  
 PC와 연결한 Actuator의 Model에 따라 또는 사용자 설정 사항에 따라 각각의 값을 선택합니다. 
 모든 옵션은 중복으로 선택할 수 있으며 검색 시 순차적으로 진행이 됩니다.  
 All 버튼을 누르게 되면 모든 선택 사항들이 선택이 되며, 아무것도 선택하지 않고 검색 시 경고 창이 나오게 됩니다.  
   ![[yrdy-2023-07-25_10.39.gif]]
  (이미지 조금 작게 border 도 얇게)
  다음은 모델에 따른 기본 설정 값에 대한 예시 입니다.  
 (자세한 내용은 해당 모델의 매뉴얼을 참조하여 주시기 바랍니다.)   
 
|   예시 모델         |   Protocol                  |   Baudrate           |
|:------------------|:----------------------------|:---------------------|
|   **Mini L12/12Lf**   | Own Protocol                |             57600pbs |
|   **Mini 17Lf**       | Modbus Protocol             |             57600pbs |  

### Actuator 검색
 SCAN 버튼을 누르게 되면 선택한 옵션에 따라 차례로 검색을 시작하여 해당 결과를 표시합니다.
 원하는 Actuator 가 모두 검색 되었을 경우, 완료를 기다리지 않고 STOP 버튼을 눌러 검색을 종료하면 됩니다.  
# 기본정보 확인
# Parameter 설정 및 제어
## 화면 구성
![[mainView-description.jpg]]

# 펌웨어 업데이트
# Recovery




## 3.1 화면 설명

## 3.2 Information
서보 모터의 정보를 표시하는 창입니다. 선택된 서보 모터의 모델명, 모터 타입, 최대 속도, 펌웨어 버전 등을 확인할 수 있습니다.  
또한 해당 서보 보터의 Datasheet 및 사용자 매뉴얼 등을 확인 할 수 있습니다.

## 3.3 Control 화면
Parameter 화면은 MightyZap 서보 모터의 제어 값을 설정하거나 동작을 테스트 할 수 있습니다.또한, 실시간 변화 Data를 그래프로 볼 수 있습니다.  
서보모터의 ID 또는 Baudrate과 같은 Parameter를 변경하거나, Goal Position등의 동작 Parameter를 간단한 방법으로 테스트가 가능합니다.
## 3.4 Update 화면
Update 창은 서보모터의 펌웨어 버전을 변경하거나, 검색되지 않는 서보모터를 복구하는데 사용됩니다.  

# 4. 기본 기능
## 4.1 통신 Port 확인

## 4.2 통신 연결 및 검색

1. 통신 연결을 위해 아래의 그림과 같이 Software를 실행 한 후 우측 상단의 SCAN 버튼을 클릭합니다.
