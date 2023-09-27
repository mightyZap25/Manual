
# 1 Total Manager 시작하기
MightyZap Total Manager 사용자 가이드  
<p align="right">LAST REVISION: 2023.07.22</p>

mightyZap Total Manager는 다양한 운영!체제에서 MightyZap Actuator를 쉽게 관리 및 제어할 수 있는 Software입니다.
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


### 2.2.2 Mac OS
Mac OS 전용 패키지를 다운도르 합니다.  
[MAC OS Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
macOS에서 MightyZap Total Manager를 설치하려면 다운로드한 파일을 어플리케이션 폴더에 복사하기만 하면 됩니다.  
![[Pasted image 20230721150751.png]]
이제 macOS에서 MightyZap Total Manager를 사용하실 수 있습니다.  
### 2.2.3 Linux
Linux 전용 패키지를 다운도르 합니다.
	- [Linux Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
terminal  창을 열고 다음과 같이 설치를 합니다.
Ubnuntu (>=22.04)
>sudo dpkg total-manager

## 2.3 화면 구성
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
### 2.4.2 mac OS
USB Interface Board Driver를 다운로드 합니다.  
	-  [USB Interface Board Window Driver]  
다운로드한 파일을 실행하고 가이드에 따라 드라이버를 설치합니다.  
	[이미지 ]  
USB Interface Board를 PC와 연결합니다.  
[시스템 정보]-[Hardware]-[USB]에서 Serial Port가 정상적으로 연결되었는지 확인합니다.    
정장적으로 연결되어 있을 경우 이미지에서와 같이 새로운 com port가 추가되는것을 확인할 수 있습니다.  
[이미지]  

### 2.4.3 Linux[ubuntu 22.04]
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

# 3 Total Manager Description
## 3.1 통신 연결 및 검색
아래의 이미지와같이 프로그램을 실행 한 후 상단 매뉴바에서 Scan 버튼을 누르면 Actuator Scan을 위한 팝업창이 활성화 됩니다.   
![[scanbutton.png]]
### 3.1.1 화면 구성
Actuaotor Scan 팝업창이 나오면  위의 OS별 Serial Port 확인을 참조하여 연결된 Comport를 확인한 후 Open 버튼을 클릭합니다.    
정상적으로 comport 연결 되었을 경우 오른쪽 그림과 같이 비활성화 되었던 창이 활성화가 되며 Actutor를 검색 할 준비가 됩니다.
![[scanning.png]]
Scan Actuator 창은 아래와 같이 구성되어있습니다.
**Scan Actuator 화면 구성**
- Serial Port Select (default :Won Protocl)
- Baudrate Select (default :57600bps)
- Scan 결과 창
- Scan, close 버튼 창
### 3.1.2 통신 설정
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

### 3.1.3 Actuator 검색
 SCAN 버튼을 누르게 되면 선택한 옵션에 따라 차례로 검색을 시작하여 해당 결과를 표시합니다.
 원하는 Actuator 가 모두 검색 되었을 경우, 완료를 기다리지 않고 STOP 버튼을 click하면 검색을 종료하면 됩니다.  
 (검색하는 gif 이미지)
 검색이 완료되었으면 Close 버튼을 click하여 팝업창을 닫습니다.
## 3.2 Information
MightyZap Actuator의 Model명, Rated Load, Stroke, firmware Version등 관련된 정보를 표시하는 페이지 입니다.  
매니저가 실행이 되면 처음 표시하는 창이  창이며, 아래의 이미지와 같이 사이드 바 매뉴의 첫번째 아이콘을 클릭하면 해당 페이지로 이동합니다.
<이미지>
### 3.2.1 서보모터 List 확인
아래의 그림과 같이 매니저에 왼쪽에는 검색된 서보모터가 Display 됩니다.  
Actuator List는 Baudrate와 Protocol에 따라 분류되어 표시 되며,  Baudrate 별로 접거나 펼 수 있다.
<이미지>

### 3.2.2 정보 확인
Actuator List를 선택하면 해당 Actuator의 정보가 표시되며, 이중 중요한 읿부 정보가 Manager의 하단 Footer에 표시됩니다.
<이미지>
Footer에 표시된 정보는 information Page가 아닌 다른 Page에서도 볼 수 있습니다. 
<이미지>
## 3.3 Parameter
MightyZap Actuator를 설정 및 간단한 동작 테스트를 하고, 동작 상태를 모니터링하는 페이지 입니다.  
Menu 선택 창에서 아래의 그림과 같은 아이콘을 클릭하면 해당 페이지로 이동합니다.
<이미지>
사용자 환경에 맞게 Stroke, ID, Baudrate 등을 설정하고 간단한 동작 테스트를 진행할 수 있습니다.  
각 Parameter에 대한 설명은 해당 모델의 사용자 매뉴얼에서 Parameter 설명을 참조하시 바랍니다.
### 3.3.1 화면 구성
Parameter 페이지의 구성은 Non-Volatile Memory 영역과 Volatile Memory 영역으로 나뉩니다.
Non-volatile Meomory는 비휘발성 메모리 영역의 Parameter로 수정 및 저장된 Data가 전원 off 되도 지워지지 않고 저장되어있습니다.  
Volatile Memory는 휘발성 메모리 영역으로 전원이 꺼지기 전까지는 해당 Data를 저장하고 있지만, 전원이 꺼지게 되면 해당 Data는 초기화 됩니다.  
Parameter 영역은 매니저의 크기를 줄일 경우, 주로 사용되어지는 Volatile-Memeory 영역이 상단으로 이동합니다.
<gif 이미지>  

**Tooltip 기능**
각 Paremater 이름의 옆에는 (?)를 한 아이콘이 있습니다. 해당 아이콘에  mouse를 가져가 대면 해당 파라메터에 대한 간단한 설명이 표시됩니다.
### 3.3.2 Parameter Control
- **Slide Control** : <font color="#4f81bd">Non-volatile Memory</font>  
  Non-Volatile Memeory의 가장 일반적인 Data 변경 방식으로 Slide bar의 Drag 또는 TextBox에 직접 Data를 입력하는 방법으로 Data를 변경 합니다.  
  값을 변경할 경우 오른쪽의 TextBox의 값이 푸른색으로 변경되며, 변경한 data를 저장하기 위해서는 S  버튼을 클릭해야 합니다. 
  ![[sliding_control_in_NOnvolatile.png]]
  <마우스로 값을 바꾸고 저장하는 이미지로>  
  S 버튼을 클릭하지 않고 다른 Parameter를 변경하려 할 경우 Data는 원래 상태로 복구 되며 TextBox의 font가 다시 흰색으로 변경됩니다.  
- **Slide Control** : <font color="#4f81bd">Volatile Memory</font>  
  Volatile Memory에서의 Slide Control 방식은 Non-Volatile Memory 방식과 유사하지만, S 버튼이 없으며, Slide bar를 Drag할 경우 변경된 Data가 즉시 적용됩니다.  
  또한 TextBox를 통해 Data를 입력할 경우 Data를 변경한 후 Enter key를 입력하면 변경된 Data가 즉시 적용됩니다.
  또한 Data가 변경되도 TextBoxd의 Font는 푸른색으로 변경되지 않습니다.
  ![[sliding_control_in_NOnvolatile.png]]  
  ><font color="#4f81bd">Tip</font>  
  >Goal Position TextBox를 클릭한 후 다음과 같이 키보드 키로 제어가 가능합니다.  
  > 	'a' : 최소 stroke로 이동
  > 	's' : stroke 중간 위치로 이동
  > 	'd' : 최대 Stroke로 이동  
- **check Control Box** : <font color="#4f81bd">Non-volatile Memory</font>   
  Check Control은 check 기능을 이용하여 Data를 변경 가능하며, 이때 Textbox는 Read Only 상태로 Data값과 상태만을 확인할 수 있습니다.
  checkbox는 모두 선택, 모두 해제, 부분 선택 모두 가능하며,선택 값이 변경되었을 경우 TestBox의 font가 푸른색으로 변경됩니다.  
  수정한 값을 적용하기 위해서는 S 버튼을 눌러 수정된 값을 저장해야 합니다.  
  ![[parameter_control_checkbox.png]]   
  버튼을 클릭하지 않고 다른 Parameter를 변경하려 할 경우 Data는 원래 상태로 복구 되며 TextBox의 font가 다시 흰색으로 변경됩니다.   
- **select Control box** : <font color="#4f81bd">Non-volatile Memory</font>   
   Select Control box는 Select 기능을 이용하여 Data를 변경 가능하며, 이때 Textbox는 Read Only 상태로 Data값과 상태만을 확인할 수 있습니다.
  select 값이 변경되었을 경우 TestBox의 font가 푸른색으로 변경되며, 
  수정한 값을 적용하기 위해서는 S 버튼을 눌러 수정된 값을 저장해야 합니다.
  ![[parameter_control_selectbox.png]]    
  버튼을 클릭하지 않고 다른 Parameter를 변경하려 할 경우 Data는 원래 상태로 복구 되며 TextBox의 font가 다시 흰색으로 변경됩니다.  
- **select box** : <font color="#4f81bd">Volatile Memory</font>   
  Volatile Memory 의 Select Control Box에는 TextBox가 존재하지 않습니다.
  Select 기능을 이용하여 선택된 Data를 즉시 적용합니다.
  ![[parameter_control_selectbox2.png]]
- **button Control box** : <font color="#4f81bd">Volatile Memory</font>   
   Button control Box 기능은 Volatilte Memory에만 있는 기능으로 Motor의 동작을 정지하기 위해 사용됩니다.
   아래의 그림과같이 Button은 활성화 비활성화에 따라 2가지의 이미지를 가지고 있으며, 해당 파라메터에 대한 자세한 설명은 해당 제품의 사용자 매뉴얼을 참조하여 주시기 바랍니다.
   ![[parameter_control_button.png]]  
### 3.3.3 Monitoring
Monitoring 기능은 MightyZap Actuator의 현재 위치, 모터 입력값, 전류 등을 실시간으로 확인하는 기능을 가지고 있습니다.  
최대 하나의 Parameter만 확인이 가능하며, 통신 속도에 따라 읽는 속도가 달라집니다.
Parameter는 Model에 따라 다르게 표시되며, check box를 통해 하나의 Paramter만 선택하실 수 있습니다.
Monitoring 기능은 아래와 같이 구성 되어있습니다.
- Data 범위  
  Data 표현 범위는 선택된 Paramter떼라 변경이 됩니다.
- Sample 표현 갯 수
  100 개의 Sample을 표시하며, 이전 Data는 볼 수 없습니다.
- Parameter Select  
  Model에 따라 선택할 수 있는 Parameter가 변경됩니다. 일반적으로 Parameter 명 앞부분에 'Present'가 들어있는 Paramter가 표시 됩니다.
- Interval  
  Interval은 Data Sample 당 읽어오는 시간 간격을 의미합니다.  
  38400bps 이상일 경우 25ms 19200bps 이하 일경우에는 50ms로 동작합니다.  
### 3.3.4 Error State  
Error state는 매니저 하단 Footer 영역 중앙에 표시됩니다.   
Error 상태는 아래와 같이 2가지를 표시합니다.    
 - **Hardware Error**    
   Actuator의 동작 에러 상태를 의미합니다. Input Voltage, Overload 등 모델에 따라 설정되어 이있는 Error 들을 의미하며, Actuator 자체에 문제가 있는 경우를 의미합니다.    
   ![[Hardware Error.png]]
 - **Communcation Error**    
   통신 에러를 의미하며 통신 중 발생할 수 있는 Packet Error, Time Out등을 표시합니다.    
   일시적인 Error의 경우 통신 중 상태를 Text로 표시하는데 그치지만, 일정 시간 이상 Error가 지속되거나 잦은 Error 발생 시 mionitoring 기능이 정지 되고 팝업창으로 경고 글이 표시됩니다.    ![[communication Error.png]]   
## 3.4 Update    
펌웨어를 업데이트 하는 페이지 입니다.  Firmware의 버전은 최신 버전을 유지하는 것을 추천 드립니다. 다만 수정된 펌웨어를 적용하기 전에  변경 사항이 사용자의 Apllication과 적합한지 테스트 하신 후에 적용하시기 바랍니다.   
펌웨어 파일은 당사의 homepage에서 다운로드 받으시기 바랍니다.  
www.mightyzap.com  
### 3.4.1 화면 구성    
Update Page는 이미지와 같이 펌웨어 업데이트, Actuator Recovery 영역으로 되어있으며, 각각의 실행은 상단 header의 메뉴에서 해당 아이콘을 선택하여 실행할 수 있습니다.  
### 3.4.2 Firmware Update   
**액츄에이터 연결**  
업데이트를 진행할 서보모터를 연결하고 SCAN 을 합니다.  
><font color="red">주의 사항  </font>  
>펌웨어 업데이트 시에는 업데이트를 진행할 actuator 하나만 연결하고 SCAN 작업을 진행하여 Actuator List에 하나의 actuator만 남아 있어야 합니다.  하나 이상의 actuator 가 연결 된 상태에서 업데이트를 진행하면 업데이트가 비정상적으로 진행되어 실패하게 되고 해당  actuator 는 동작이 되지 않게 됩니다.  
  
**업데이트 파일 선택**  
firmware update를 진행 할 경우 그림과 같이 Select file 버튼을 눌러 다운로드 받은 업데이트 파일을 선택해야 합니다.    
<파일 선택 이미지 gif>  
><font color="#ff0000">주의 사항  </font>
>이때 다른 모델의 firmware file 을 선택하지 않게 조심해야 합니다. Actuator List에 나와있는 Model 명과 uipdate file의 이름이 동일한지 확인해야 합니다.

**업데이트**  
모든 사항이 준비가 다 되었으면 상단 메뉴바에서 Update 아이콘을 클릭합니다.   
이때 둘 이상의 actuator 가 연결되었을 경우 다음과 같은 경고창이 나타나고 SCAN  작업을 다시 합니다.  
<경고창 이미지 >  
**업데이트 완료**
업데이트가 진행되면 그림과 같이 prograss bar가 진행이 됩니다. 100%까지 완료되면 update 완료 메세지가 나타납니다.   
필요에 따라 reset이나 Factory Rest을 추가적으로 진행하시면 됩니다.  
  
**펌웨어 업데이트 실패**  
### 3.4.3 Recovery  
Firmware 가 업데이트 실패 씨 또는 SCAN을 통해 서보모터를 검색하지 못할 경우 리커버리를 진행합니다.   
문제가 발생한 액츄에이만을 연결한 후 상단 매뉴바의 리커버리 아이콘을 클릭합니다.  
검색시  
미겁색시 펌웨어 업데이트 진행  
calibration 진행  
완료
### 3.4.4 Factory Reset   
Actuator의  상태를 공장 출하 시의 초기 상태로 돌리고, 위치 값을 결정하는 Potentiometer의 Calibration을 진행합니다.  
><font color="#ff0000">주의사항</font>  
>Factroy Reset 중에 Actuator가 Calibration을 위해 최대./최소로 위치이동을 합니다. 정상적인 Calibration을 위해 장치에 연결하지 않고 무부하에 최대 동작거리를 유지할 수 있는 공간에서 진행해 주시기 바랍니다.

**Factory Reset Icon**  
Factory Reset은 Update Page에 들어오면 상단 매뉴에 추가 되어있는 것을 확인할 수 있습니다.  

**Factory Reset 화면구성**  
Factory Reset을 선택하면 팝업 창이 나타납니다. 팜업창에는 Factory Reset 관련 Option 선택창과 Text Area가 나타나고 하단에 Factory Reset 을 위한 버튼이 존재합니다.  

**Options**  
Factory Reset에 대한 Option은 2가지로 ID Remind와 Baudrate Reminde 입니다. 그외의 다른 파라메터들은 모두 초기화 됩니다.  
<이미지>
일전적인 Reset 에서는 초기화 되지 않는 Protocol, Min/Max Position Calibration이 초기화 되고, Potentiometer의 Calibration을 실행하면서 해당 내부 Parameter도 수정이 됩니다.  
Factopry Reset 후에도 유지하고 싶은 Option을 선택하시면 됩니다.  

**Factory Reset**  
하단의 Factory Reset 버튼을 클릭하면, Factory Reset을 실행합니다. 실행중 진행되는 사항을 Option 선택 아래의 Text Area 창에 표시합니다. 
<gif 이미지>
Factory Reset 진행이 되면서 Actuator가 몇번의 시스템 제시작을 하면서 LED가 깜빡입니다. 또한 Potenmtiometer Calibration 시에는 Actuator가 최대로 확장 및 수축 행동을 하면서 Calibration 을 진행합니다.  
최종적으로 Factory Reset이 완료되면 하단의 Close 버튼이 활성화 되면서 Parameter 창으로 이동하여 reset된 Data를 보여줍니다.
<gif 이ㅁ미지>

## 3.5 Setting
Total Manager의 언어 및 Theme를 변경할 수 있는 기능입니다.
<이미지>
### 3.5.1 Language  
Total Manager의 언어는 영어와 한국어를 지원합니다.  해당 언어를 선택하면 즉시 바로 적용이 되며 모든 tooltip, Popup 창이 해당 언어로 변경이 됩니다.  변경된 내용은 저장이 되어 프로그램을 재시작 해도 변경 상태를 유지합니다.  
<이미지 toolip 및 팝업 선택 영상 포함>
### 3.5.2 theme  
 Total Manager는 dark Mode와 white Mode 2가지를 제공합니다. 해당 theme를 선택하면 즉시 적용이 되며 변경된 내용은 저장이 되어 프로그램 재 시작시에도 변경 상태가 유지됩니다.
 <이미지>
~~### 3.6 Software Update  
업데이가 발생할 경우 팝업이 생성이 되면서 다운로드 유무를 물어본다.......~~ 



