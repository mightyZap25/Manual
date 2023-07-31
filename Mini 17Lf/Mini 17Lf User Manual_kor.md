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
## Non-volatile Memory (ROM)  



## Volatile Memory(RAM)
