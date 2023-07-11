# 1. 개요
## 1.1 제품 소개
mightyZap Total Manager는 다양한 운영체제에서 MightyZap Actuator를 쉽게 관리 및 제어할 수 있는 Software입니다.
Total Manager의 특징은 아래와 같습니다.
- 통신이 가능한 MightyZap의 Parameter를 설정하고, 동작 테스트를 할 수 있습니다.
- 간단한 동작 Motion 을 테스트하고 시간에 따라 변경되는 Data를 확인할 수 있습니다.
- 다양한 Protocol을 기반으로 MightyZap을 상태 확인 및 제어 할 수 있습니다.
- 모든 Smart mightyZap의 펌웨어를 업데이트 할 수 있습니다.

![[controlfuulshot.png]]

MightyZap Total Manager를 구동하기 위해서는 MightyZap 서보 인터페이스 모듈을 추천드립니다.
## 1.2 지원 Protocol
- Protocol 1.0
- Modbus-RTU (FC-Only)
- CAN Protocol (BLDC Only)
## 1.3 지원 운영체제
- Windows : windows 7(32bit) 이상
- Mac OS : Big Sur
- Linux : Ubuntu LTD 20.04
	- DeskTop & lapTop에서만 테스트 되었습니다.
## 1.4 Interface Board
adklfjasdf
aslkdfjaskld

# 2. Software Install
## 2.1 윈도우에서 설치하기
1. 윈도우즈 전용 패키지를 다운도르 합니다.
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
![[Information.jpg]]
## 3.3 Control 화면
Parameter 화면은 MightyZap 서보 모터의 제어 값을 설정하거나 동작을 테스트 할 수 있습니다.또한, 실시간 변화 Data를 그래프로 볼 수 있습니다.