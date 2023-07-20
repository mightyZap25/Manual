
# Total Manager 시작하기
MightyZap Total Manager 사용자 가이드
LAST REVISION: 2023.07.20

mightyZap Total Manager는 다양한 운영체제에서 MightyZap Actuator를 쉽게 관리 및 제어할 수 있는 Software입니다.
Total Manager에서는 다양한 OS를 제공하고, 사용자 인터페이스를 개선하고 신규 MightyZap 모델을 추가로 지원하는 신규MightyZap Manager 입니다.
이 가이드에서는 Total Manager의 설치와 각 기능의 사용법에 대한 기본 사항을 다룹니다.
[Total Manager Software Download](https://mightyzap.com/ko/digitalarchive6/?uid=211&mod=document&pageid=1) 페이지에서 다운로드 할 수 있습니다.
## 개요
mightyZap Total Manager는 다양한 기능을 가진 다목적 Software입니다. MightyZap Actuator의 동작 Test와 Parameter 설정 및 동작 상태 Monitoring과 Firmware Update를 기본적으로 제공합니다.
또한 모델에 따른 특수 기능을 설정 및 테스트 할 수도 있습니다.
특수 기능 설정 및 테스트 내용은 각 모델의 매뉴얼을 참조하시기 바랍니다.

![[total_image.png]]
## 지원 운영체제
- Windows : windows 7(32bit) 이상
- Mac OS : Big Sur
- Linux : Ubuntu LTD 20.04
	- DeskTop & lapTop에서만 테스트 되었습니다.
## 사용 환경
MightyZap Actuator는 Half Duplex TTL, RS485, CAN 통신을 사용합니다. PC와의 통신을 위한 컨버터를 사용해야 Actuator와의 통신이 가능합니다.
당사에서는 MightyZap Actuator를 위한 USB Interface Board를 판매하고 있습니다. 당사의 Interface Board를 사용할 경우 손쉽게 MightyZap을 PC와 연결할 수 있습니다.
시중의 Convertor를 구매하여 사용하실 수 있지만, 안전성을 위하여 가급적 당사의 Interface Board를 사용하여 주시기 바랍나다.

 <font color="#ff0000">주의 사항</font>
 PC와 Interface Board와의 연결에 사용하는 Cable중 통신이 되지않는 충전 전용 Cable을 사용하여 통신이 연결되지 않는 경우가 있습니다. 반드시 확인하시고 사용하여 주시기 바랍니다.

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
### Update
MightyZap Actuator의 Firmware를 Update할 때 사용합니다. 당사의 Webpage에서 해당 모델에 맞는 업데이트 파일을 다운로드 받으신 후 업데이트를 진행 하실 수 있습니다.
또한, Update Fail 및 사용자의 실수로 인해 서보모터가 검색이 되지 않을 경우 Firmware를 검사 및 복구 하실 수도 있습니다.
![[update-view.jpg]]

# Software Install
### Windows에서 설치하기[이미지는 영문을 기본으로 ]
1. 윈도우즈 전용 패키지를 다운도르 합니다.
	- [Windows Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
2. 다운받은 설치 파일을 실행합니다.
 ![[windows0install.jpg]]
3. Next 버튼을 클릭하여 설치를 진행합니다.   
   ![[windows-install-next.jpg]]
### Mac OS에서 설치하기
윈도우즈 전용 패키지를 다운도르 합니다.
	- [Windows Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
2. 다운받은 설치 파일을 실행합니다.
 ![[windows0install.jpg]]
3. Next 버튼을 클릭하여 설치를 진행합니다.   
   ![[windows-install-next.jpg]]
### Unbuntu에서 설치하기
윈도우즈 전용 패키지를 다운도르 합니다.
	- [Windows Software 다운로드](https://github.com/mightyZap25/Total-Manager/releases/download/v0.8.1/latest.yml)
2. 다운받은 설치 파일을 실행합니다.
 ![[windows0install.jpg]]
3. Next 버튼을 클릭하여 설치를 진행합니다.   
   ![[windows-install-next.jpg]]

# 3. 매뉴 설명
## 3.1 화면 설명
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
