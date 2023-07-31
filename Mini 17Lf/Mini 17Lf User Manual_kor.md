# 주의 사항
이 문서는 사용자가 M?ini 17Lf 제품을 사용하는데 도움이 되도록 작성되었습니다.   
사용자는 기본적으로 Coreless Motor, 모션제어와 Modbus RTU에 대한 기본적인 이해를 가지고 있다고 가정합니다.  

# 1. Introduction
Mini 17Lf Model은 다양한 기능을 내장한 Actuator로 효율적이고 유연한 모션 제어 어플리케이션을 위한 완볍한 솔루션입니다. <문구 수정>
## 1.1 Overview
- RS-485 Modbus RTU
- 17Pi Coreless Motor
- Extend I/O Port (Joystick, Switch Contorl, etc)
- Current Feedback Control
- Speed Control
- 12bit(4096) Position Resolution
- 역전압 및 ESD 방지 회로 ...
- 내부 Motion Action 기능

- 전기적 특성
	- 동작 전압 소 tyupe 대
	- 입력전압 소 대
	- 보호기능
	- 제어방식
	- 인터페이스
	- 환경조건
	- 온습도
	- 온도
	- 진동
	- 질량

- 주요사항 
	- 성능 곡선

아코디언 폴더
 - 유저 매뉴얼
 - 프로토콜 매뉴얼
 - 데이터시트
 - 참고자료
	 - 인증 자료
	 - 도면
	 - 케이블 및 커넥터
	 - 통신 회로
	 - 악세사리




# Control Table
Control Table은 Actuator를 구동 및 제어하기위한 데이터와 현재 상태를 나타내는 Parameter들로 이루어져 있습니다.   
사용자는 통신 Packet을 이용하여 특정 Parameter의 Data를  읽어 Actuator의 상태를 확인하거나, Data를 변경하여 Actuator를 제어할 수 있습니다.  
통신 Packet에 대한 자세한 내용은 Modbus-RTU를 참고하여 주시기 바랍니다.  
(Mini 17Lf Model은 Modbus-RTU 통신만을 제공합니다)
## 1 Description  
### 1.1 Memory Type (Non-Volatile, Volatile)  
Control Table은 2가의 영역으로 구분됩니다. Data를 변경한 후 전원을 꺼도 그 Data가 유지가 되는  Non-volatile Memory(ROM)와 전원이 꺼지면 Data가 초기화 되는 Volatile Memory(RAM)가 있습니다.  
### 1.2 Address  
본 문서에서의 Address는 control Table에서의 Data Adress를 의미합니다.
### 1.3 Size  
Mini 17Lf Model의 모든 Parameter의 Data Size 2byte 로 되어있습니다.
### 1.4 Access  (접근 권한)
Control Table Data는 'R', 'RW'로 표기됩니다. 'R'은 읽기 전용(Read Only) 의미하고, 'RW'는  읽기와 쓰기가 모두 가능합니다.  
읽기 전용 권한은 주로 서보모터의 기본정보 또는 모니터링용으로 사용됩니다. 읽기 쓰기 권한은 MightyZap 제어 용도로 사용됩니다.  
### 1.5 Default  
기본값은 초기 설정값(공장 출하 설정값)입니다. Non-Volatile Memory 영역의 값은 사용자가 수정할 경우 변경한 값으로 적용되며, volatile Memory 영역은 전원이 인가 되었을 때의 값을 의미합니다.  
## 2 Non-volatile Memory (ROM)  

|Address|Name|Description|Access|Default|
|---|---|---|---|---|
|0 (0x00)|Serial Number|Model Serial Nu mber|R||
|1 (0x01)|Firmware Version|펌웨어 버전 정보|R||
|4 (0x04)|Actuator ID|Actuator ID|RW|1(0x01)|
|5 (0x05)|Actuator Baudrate|통신 속도|RW|32(0x20)|
|9 (0x09)|Alarm Led|하드웨어 에러 알랍 LED 표시|RW|33(0x21)|
|10 (0x0A)|Alarm Shutdown|하드웨어 에러 셧다운 기능|RW|33(0x21)|
|11 (0x0B)|Short Stroke Limit|수축 방향 한계 위치 값|RW|0(0x00)|
|12 (0x0C)|Long Stroke Limit|확장 방향 한계 위치값|RW|개별 Spec|
|13 (0x0D)|Start Compliance Margin|시작 Compliance Margin|RW|20(0x14)|
|14 (0x0E)|End Compliance Margin|종료 Compliance Margin|RW|8(0x08)|
|15 (0x0F)|Acceleration|가속도|RW|개별 Spec|
|16 (0x010)|Deceleration|감속도|RW|개별 Spec|
|17 (0x011)|Min Position Calibration|Min Position Trim|RW|개별 Spec|
|18 (0x012)|Max Position Calibration|Max Position Trim|RW|개별 Spec|
|19 (0x013)|Motor Operating Rate Limt|모터 가동률 한계값(PWM)|RW|1000|
|20 (0x014)|Speed Limit|속도 상한 값|RW|1000|
|21 (0x015)|Current Limit|전류 상한 값|RW|800|
|22 (0x016)|Current I Gain|전류 I Gain|RW|개별 Spec|
|23 (0x017)|Current P Gain|전류 P Gain|RW|개별 Spec|
|24 (0x018)|Speed D Gain|속도 D Gain|RW|개별 Spec|
|25 (0x019)|Speed I Gain|속도 I Gain|RW|개별 Spec|
|26 (0x01A)|Speed P Gain|속도 P Gain|RW|개별 Spec|
|40 (0x028)|Internal Addess 0|간접 주소 0|RW|0(0x00)|
|41 (0x029)|Internal Addess 1|간접 주소 1|RW|0(0x00)|
|42 (0x02A)|Internal Addess 2|간접 주소 2|RW|0(0x00)|
|43 (0x02B)|Internal Addess 3|간접 주소 3|RW|0(0x00)|
|44 (0x02C)|Internal Addess 4|간접 주소 4|RW|0(0x00)|
|45 (0x02D)|Internal Addess 5|간접 주소 5|RW|0(0x00)|
|46 (0x02E)|Internal Addess 6|간접 주소 6|RW|0(0x00)|
|47 (0x02F)|Internal Addess 7|간접 주소 7|RW|0(0x00)|
|48 (0x030)|Internal Addess 8|간접 주소 8|RW|0(0x00)|
|49 (0x031)|Internal Addess 9|간접 주소 9|RW|0(0x00)|
|50 (0x032)|Extened Port Setting 0|확장 Port 0 기능 설정|RW|0(0x00)|
|51 (0x033)|Extened Port Setting 1|확장 Port 1 기능 설정|RW|0(0x00)|
|52 (0x034)|Extened Port Setting 2|확장 Port 2 기능 설정|RW|0(0x00)|
|53 (0x035)|Extened Port Setting 3|확장 Port 3 기능 설정|RW|0(0x00)|
|60 (0x03C)|Action 0 type|Action 0 동작 형식|RW|0(0x00)|
|61 (0x03D)|Action 0 distance|Action 0 이동 거리|RW|0(0x00)|
|62 (0x03E)|Action 0 Repeat Type|Action 0 반복 형식|RW|0(0x00)|
|63 (0x03F)|Action 0 Repeat Count|Action 0 반복 횟수|RW|0(0x00)|
|64 (0x040)|Action 0 Repeat Time|Action 0 1회 동작 시간|RW|0(0x00)|
|65 (0x041)|Action 0 Goal Speed|Action 0 Gaol Speed|RW|0(0x00)|
|66 (0x042)|Action 0 Gal Current|Action 0 Goal Current|RW|0(0x00)|
|67 (0x043)|Action 0 Accleration|Action 0 Acceleration|RW|0(0x00)|
|68 (0x044)|Action 0 Delceration|Action 0 Deceleration|RW|0(0x00)|
|69 (0x045)|Action 0 Stop|Action 0 정지 형식|RW|0(0x00)|
|70 (0x046)|Action 1 type|Action 1 동작 형식|RW|0(0x00)|
|71 (0x047)|Action 1 distance|Action 1 이동 거리|RW|0(0x00)|
|72 (0x048)|Action 1 Repeat Type|Action 1 반복 형식|RW|0(0x00)|
|73 (0x049)|Action 1 Repeat Count|Action 1 반복 횟수|RW|0(0x00)|
|74 (0x04A)|Action 1 Repeat Time|Action 1 1회 동작 시간|RW|0(0x00)|
|75 (0x04B)|Action 1 Goal Speed|Action 1 Gaol Speed|RW|0(0x00)|
|76 (0x04C)|Action 1 Gal Current|Action 1 Goal Current|RW|0(0x00)|
|77 (0x04D)|Action 1 Accleration|Action 1 Acceleration|RW|0(0x00)|
|78 (0x04E)|Action 1 Delceration|Action 1 Deceleration|RW|0(0x00)|
|79 (0x04F)|Action 1 Stop|Action 1 정지 형식|RW|0(0x00)|
|80 (0x050)|Action 2 type|Action 2 동작 형식|RW|0(0x00)|
|81 (0x051)|Action 2 distance|Action 2 이동 거리|RW|0(0x00)|
|82 (0x052)|Action 2 Repeat Type|Action 2 반복 형식|RW|0(0x00)|
|83 (0x053)|Action 2 Repeat Count|Action 2 반복 횟수|RW|0(0x00)|
|84 (0x054)|Action 2 Repeat Time|Action 2 1회 동작 시간|RW|0(0x00)|
|85 (0x055)|Action 2 Goal Speed|Action 2 Gaol Speed|RW|0(0x00)|
|86 (0x056)|Action 2 Gal Current|Action 2 Goal Current|RW|0(0x00)|
|87 (0x057)|Action 2 Accleration|Action 2 Acceleration|RW|0(0x00)|
|88 (0x058)|Action 2 Delceration|Action 2 Deceleration|RW|0(0x00)|
|89 (0x059)|Action 2 Stop|Action 2 정지 형식|RW|0(0x00)|
|90 (0x05A)|Action 3 type|Action 3 동작 형식|RW|0(0x00)|
|91 (0x05B)|Action 3 distance|Action 3 이동 거리|RW|0(0x00)|
|92 (0x05C)|Action 3 Repeat Type|Action 3 반복 형식|RW|0(0x00)|
|93 (0x05D)|Action 3 Repeat Count|Action 3 반복 횟수|RW|0(0x00)|
|94 (0x05E)|Action 3 Repeat Time|Action 3 1회 동작 시간|RW|0(0x00)|
|95 (0x05F)|Action 3 Goal Speed|Action 3 Gaol Speed|RW|0(0x00)|
|96 (0x060)|Action 3 Gal Current|Action 3 Goal Current|RW|0(0x00)|
|97 (0x061)|Action 3 Accleration|Action 3 Acceleration|RW|0(0x00)|
|98 (0x062)|Action 3 Delceration|Action 3 Deceleration|RW|0(0x00)|
|99 (0x063)|Action 3 Stop|Action 3 정지 형식|RW|0(0x00)|
|100 (0x064)|Action 4 type|Action 4 동작 형식|RW|0(0x00)|
|101 (0x065)|Action 4 distance|Action 4 이동 거리|RW|0(0x00)|
|102 (0x066)|Action 4 Repeat Type|Action 4 반복 형식|RW|0(0x00)|
|103 (0x067)|Action 4 Repeat Count|Action 4 반복 횟수|RW|0(0x00)|
|104 (0x068)|Action 4 Repeat Time|Action 4 1회 동작 시간|RW|0(0x00)|
|105 (0x069)|Action 4 Goal Speed|Action 4 Gaol Speed|RW|0(0x00)|
|106 (0x06A)|Action 4 Gal Current|Action 4 Goal Current|RW|0(0x00)|
|107 (0x06B)|Action 4 Accleration|Action 4 Acceleration|RW|0(0x00)|
|108 (0x06C)|Action 4 Delceration|Action 4 Deceleration|RW|0(0x00)|
|109 (0x06D)|Action 4 Stop|Action 4 정지 형식|RW|0(0x00)|

## 3 Volatile Memory(RAM)

|Address|Name|Description|Access|Default|
|---|---|---|---|---|
|200 (0x0C8)|Force On/Off|모터 출력 끄고 켜기|RW|1(0x01)|
|201 (0x0C9)|Actuator Pause|모터 일시 정지|RW|0(0x00)|
|202 (0x0CA)|Actuator Stop|모터 일시 정지|RW|0(0x00)|
|203 (0x0CB)|LED Color|LED On/Off|RW|0(0x00)|
|204 (0x0CC)|Hardware Error|Hardware Error|R|0(0x00)|
|205 (0x0CD)|Goal Position|목표 위치 값|RW||
|208 (0x0D0)|Goal Speed|목표 속도 값|RW|Speed Limit|
|209 (0x0D1)|Goal Current|최대 전류 값|RW|Current Limit|
|210 (0x0D2)|Present Position|현재 위치 값|R||
|211 (0x0D3)|Present Current|현재 소비 전류 값|R||
|213 (0x0D5)|Present Motor PWM|모터 입력 PWM|R||
|214 (0x0D6)|Present Voltage|현재 전압 값|R||
|215 (0x0D7)|Moving|모터 동작 유무|R||
|220 (0x0DC)|Action Enable|Action 기능 켜기/끄기|RW||
|240 (0x0F0)|Internal Data 0|간접 주소 0 데이터 값|개별|개별 Spec|
|241 (0x0F1)|Internal Data 1|간접 주소 1 데이터 값|개별|개별 Spec|
|242 (0x0F2)|Internal Data 2|간접 주소 2 데이터 값|개별|개별 Spec|
|243 (0x0F3)|Internal Data 3|간접 주소 3 데이터 값|개별|개별 Spec|
|244 (0x0F4)|Internal Data 4|간접 주소 4 데이터 값|개별|개별 Spec|
|245 (0x0F5)|Internal Data 5|간접 주소 5 데이터 값|개별|개별 Spec|
|246 (0x0F6)|Internal Data 6|간접 주소 6 데이터 값|개별|개별 Spec|
|247 (0x0F7)|Internal Data 7|간접 주소 7 데이터 값|개별|개별 Spec|
|248 (0x0F8)|Internal Data 8|간접 주소 8 데이터 값|개별|개별 Spec|
|249 (0x0F9)|Internal Data 9|간접 주소 9 데이터 값|개별|개별 Spec|

## 4 Control Table Discription
### 4.1  Model Serial Number
MightyZap Model을 구별하기 위한 번호입니다.
### 4.2 Firmware Version  
해당 제품의 펌웨어 버전이 표기되며, Semantic Versioning 방식으로 표기합니다. 
**Semantic Versioning**
	major.mijnor.patch
	- major : 전반적인 펌웨어 개편 또는 주요 기능 수정 및 추가
	- minor : 기능 수정 및 기능이 추가된 경우
	- patch :  버그 및 코드 보완이 추가된 경우
