# 읽기 전에...
이 문서는 사용자가 M?ini 17Lf 제품을 사용하는데 도움이 되도록 작성되었습니다.   
사용자는 기본적으로 Coreless Motor, Motion 제어 등과 같은 기본적인 이해를 가지고 있다고 가정합니다.   
추가적인 정보가 필요하신 분들은 아래의 문서를 먼저 확인 하신 후 아래의 가이드를 확인 해 주시거나, 본 가이드를 읽는 중에 관련 링크를 클릭하시어 추가적인 정보를 읽어보시기 바랍니다. 
 - CLDC Motor의 특성과 이해
 - Motion 제어

# 1. Introduction
Mini 17Lf Model은 다양한 기능을 내장한 Actuator로 효율적이고 유연한 모션 제어 어플리케이션을 위한 완벽한 솔루션입니다. Mightyzap Mini Linear Actuator는 협소한 공간에서 효율적인 선형 운동이 필요한 어플리케이션에 활용 가능한 제품이며, 산업, 의료, 로봇연구, UAV 분양 등 다양한 방면에서 활용이 가능한 제품입니다.
### <font color="#ff0000">주의 사항</font>
MightyZap Actuator를 안정적으로 사용하기 위해서는 몇가지 주의 사항이 있습니다. 다음의 링크를 클릭하시여 주의 사항을 확인하여 주시기 바랍니다.
[[#주의사항]]

## 1.2 사양
### 17Lf 시리즈 주요사양
<table>
<tr>

</tr>
</table>

| 정격부하 | 최고속도<br>(무부하) |                                                       스트로크                                                       |   위치 정밀도<br>(단방향)    | 통신 타입 | Mechanical  <br>Self Lock  <br>(Z축 사용) |
|:--------: |:--------------------: |:--------------------------------------------------------------------------------------------------------------------:|:----------------------------:|:--------- |:-----------------------------------------:|
| 35N      | 85mm/s               |         27mm [17Lf-35F-27]<br>37mm&nbsp;[17Lf-35F-37]<br>50mm&nbsp;[17Lf-35F-50]<br>87mm&nbsp;[17Lf-35F-87]          | 30um<br>30um<br>40um<br>50um |           |         없음  <br>(Z축 적용 주의)         |
| 70N      | 85mm/s               | 27mm&nbsp;&nbsp;[17Lf-70F-27]<br>37mm&nbsp;[17Lf-70F-37]<br>50mm&nbsp;[17Lf-70F-50]<br>87mm&nbsp;&nbsp;[17Lf-70F-87] | 30um<br>30um<br>40um<br>50um | RS-485    |         없음  <br>(Z축 적용 주의)         |

| Item                | Description           |
|:--------------------|:----------------------|
|  동작 전압              |  8~13V [12Vdc]        |
|  Idle Current       |  20mA                 |
|  Rated Current      |  350mA                |
|  Motor type         |  Coreless DC Mtoor    |
|  Motor 출력           |  26W                  |
|  Duty Cycle         |  50%                  |
|  Communication      |  RS-485 (Modbus-RTU)  |
|  Sensor Type        |  Potentiometer        |
|  Sensor Resolution  |  10000                |
|  Noise              |  50dB at 1m           |
|  Connector          |  Molex 0510650400     |  

### Motor 성능 곡선
![[스크린샷 2023-08-10 18-04-36.png]]  
- 모터 성능 곡선에 대한 자세한 설명은 다음의 문서를 통해 확인해 주시기 바랍니다. 
# 2 Control Table
Control Table은 Actuator를 구동 및 제어하기 위한 Parameter와 현재 상태를 나타내는 Parameter로 이루어져 있습니다.   
사용자는 통신 Packet을 이용하여 특정 Parameter의 Data를  읽어 Actuator의 상태를 확인하거나, Paramter의 Data를 변경하여 Actuator를 제어할 수 있습니다.  
통신 Packet에 대한 자세한 내용은 Modbus-RTU를 참고하여 주시기 바랍니다.  
(Mini 17Lf Model은 Modbus-RTU 통신 만을 제공합니다)
## 2.1 Description  
### 2.1.1 Memory Type (Non-Volatile, Volatile)  
Control Table은 2개의 영역으로 구분됩니다. Data를 변경한 후 전원을 꺼도 그 Data가 유지가 되는  Non-volatile Memory(ROM)와 전원이 꺼지면 Data가 초기화 되는 Volatile Memory(RAM)가 있습니다.    
- **Non-Volatile Memory (ROM)** : 데이터 수정 시 약 250ms의 시간이 걸릴 수 있습니다. 또한 메모리를 저장 중에는 통신이 제한 될 수 있습니다.  일반적으로 동작 전 설정 사항을 정할 때에만 사용합니다. 
- **Volatile Memeory(RAM)** :  실시간으로 데이터를 변경할 때 사용합니다. 일반적인 동작 제어 파라메터들로 구성 되어있습니다. 전원이 재인가 되면 초기화 됩니다.  
### 2.1.2 Address  
본 문서에서 Address는 Control Table에서 Data Adress를 의미합니다.
### 2.1.3 Size  
Mini 17Lf Model의 모든 Parameter의 Data Size 2byte 로 되어있습니다.
### 2.1.4 Access  (접근 권한)
Control Table Data는 'R', 'RW'로 표기됩니다. 'R'은 읽기 전용(Read Only) 의미하고, 'RW'는  읽기와 쓰기가 모두 가능합니다.  
읽기 전용 권한은 주로 서보 모터의 기본 정보 또는 모니터링 용으로 사용됩니다. 읽기 쓰기 권한은 MightyZap 제어 용도로 사용됩니다.  
### 2.1.5 Default  
기본 값은 초기 설정 값(공장 출하 설정 값)입니다. Non-Volatile Memory 영역의 값은 사용자가 수정할 경우 변경한 값으로 적용되며, Volatile Memory 영역은 전원이 인가 되었을 때의 값을 의미합니다.  
## 2.2 Non-volatile Memory (ROM)  

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
|16 (0x10)|Deceleration|감속도|RW|개별 Spec|
|17 (0x11)|Min Position Calibration|Min Position Trim|RW|개별 Spec|
|18 (0x12)|Max Position Calibration|Max Position Trim|RW|개별 Spec|
|19 (0x13)|Motor Operating Rate Limt|모터 가동률 한계값(PWM)|RW|1000|
|20 (0x14)|Speed Limit|속도 상한 값|RW|1000|
|21 (0x15)|Current Limit|전류 상한 값|RW|800|
|22 (0x16)|Current I Gain|전류 I Gain|RW|개별 Spec|
|23 (0x17)|Current P Gain|전류 P Gain|RW|개별 Spec|
|24 (0x18)|Speed D Gain|속도 D Gain|RW|개별 Spec|
|25 (0x19)|Speed I Gain|속도 I Gain|RW|개별 Spec|
|26 (0x1A)|Speed P Gain|속도 P Gain|RW|개별 Spec|
|40 (0x28)|Internal Addess 0|간접 주소 0|RW|0(0x00)|
|41 (0x29)|Internal Addess 1|간접 주소 1|RW|0(0x00)|
|42 (0x2A)|Internal Addess 2|간접 주소 2|RW|0(0x00)|
|43 (0x2B)|Internal Addess 3|간접 주소 3|RW|0(0x00)|
|44 (0x2C)|Internal Addess 4|간접 주소 4|RW|0(0x00)|
|45 (0x2D)|Internal Addess 5|간접 주소 5|RW|0(0x00)|
|46 (0x2E)|Internal Addess 6|간접 주소 6|RW|0(0x00)|
|47 (0x2F)|Internal Addess 7|간접 주소 7|RW|0(0x00)|
|48 (0x30)|Internal Addess 8|간접 주소 8|RW|0(0x00)|
|49 (0x31)|Internal Addess 9|간접 주소 9|RW|0(0x00)|
|50 (0x32)|Extened Port Setting 0|확장 Port 0 기능 설정|RW|0(0x00)|
|51 (0x33)|Extened Port Setting 1|확장 Port 1 기능 설정|RW|0(0x00)|
|52 (0x34)|Extened Port Setting 2|확장 Port 2 기능 설정|RW|0(0x00)|
|53 (0x35)|Extened Port Setting 3|확장 Port 3 기능 설정|RW|0(0x00)|
|60 (0x3C)|Action 0 type|Action 0 동작 형식|RW|0(0x00)|
|61 (0x3D)|Action 0 distance|Action 0 이동 거리|RW|0(0x00)|
|62 (0x3E)|Action 0 Repeat Type|Action 0 반복 형식|RW|0(0x00)|
|63 (0x3F)|Action 0 Repeat Count|Action 0 반복 횟수|RW|0(0x00)|
|64 (0x40)|Action 0 Repeat Time|Action 0 1회 동작 시간|RW|0(0x00)|
|65 (0x41)|Action 0 Goal Speed|Action 0 Gaol Speed|RW|0(0x00)|
|66 (0x42)|Action 0 Gal Current|Action 0 Goal Current|RW|0(0x00)|
|67 (0x43)|Action 0 Accleration|Action 0 Acceleration|RW|0(0x00)|
|68 (0x44)|Action 0 Delceration|Action 0 Deceleration|RW|0(0x00)|
|69 (0x45)|Action 0 Stop|Action 0 정지 형식|RW|0(0x00)|
|70 (0x46)|Action 1 type|Action 1 동작 형식|RW|0(0x00)|
|71 (0x47)|Action 1 distance|Action 1 이동 거리|RW|0(0x00)|
|72 (0x48)|Action 1 Repeat Type|Action 1 반복 형식|RW|0(0x00)|
|73 (0x49)|Action 1 Repeat Count|Action 1 반복 횟수|RW|0(0x00)|
|74 (0x4A)|Action 1 Repeat Time|Action 1 1회 동작 시간|RW|0(0x00)|
|75 (0x4B)|Action 1 Goal Speed|Action 1 Gaol Speed|RW|0(0x00)|
|76 (0x4C)|Action 1 Gal Current|Action 1 Goal Current|RW|0(0x00)|
|77 (0x4D)|Action 1 Accleration|Action 1 Acceleration|RW|0(0x00)|
|78 (0x4E)|Action 1 Delceration|Action 1 Deceleration|RW|0(0x00)|
|79 (0x4F)|Action 1 Stop|Action 1 정지 형식|RW|0(0x00)|
|80 (0x50)|Action 2 type|Action 2 동작 형식|RW|0(0x00)|
|81 (0x51)|Action 2 distance|Action 2 이동 거리|RW|0(0x00)|
|82 (0x52)|Action 2 Repeat Type|Action 2 반복 형식|RW|0(0x00)|
|83 (0x53)|Action 2 Repeat Count|Action 2 반복 횟수|RW|0(0x00)|
|84 (0x54)|Action 2 Repeat Time|Action 2 1회 동작 시간|RW|0(0x00)|
|85 (0x55)|Action 2 Goal Speed|Action 2 Gaol Speed|RW|0(0x00)|
|86 (0x56)|Action 2 Gal Current|Action 2 Goal Current|RW|0(0x00)|
|87 (0x57)|Action 2 Accleration|Action 2 Acceleration|RW|0(0x00)|
|88 (0x58)|Action 2 Delceration|Action 2 Deceleration|RW|0(0x00)|
|89 (0x59)|Action 2 Stop|Action 2 정지 형식|RW|0(0x00)|
|90 (0x5A)|Action 3 type|Action 3 동작 형식|RW|0(0x00)|
|91 (0x5B)|Action 3 distance|Action 3 이동 거리|RW|0(0x00)|
|92 (0x5C)|Action 3 Repeat Type|Action 3 반복 형식|RW|0(0x00)|
|93 (0x5D)|Action 3 Repeat Count|Action 3 반복 횟수|RW|0(0x00)|
|94 (0x5E)|Action 3 Repeat Time|Action 3 1회 동작 시간|RW|0(0x00)|
|95 (0x5F)|Action 3 Goal Speed|Action 3 Gaol Speed|RW|0(0x00)|
|96 (0x60)|Action 3 Gal Current|Action 3 Goal Current|RW|0(0x00)|
|97 (0x61)|Action 3 Accleration|Action 3 Acceleration|RW|0(0x00)|
|98 (0x62)|Action 3 Delceration|Action 3 Deceleration|RW|0(0x00)|
|99 (0x63)|Action 3 Stop|Action 3 정지 형식|RW|0(0x00)|
|100 (0x64)|Action 4 type|Action 4 동작 형식|RW|0(0x00)|
|101 (0x65)|Action 4 distance|Action 4 이동 거리|RW|0(0x00)|
|102 (0x66)|Action 4 Repeat Type|Action 4 반복 형식|RW|0(0x00)|
|103 (0x67)|Action 4 Repeat Count|Action 4 반복 횟수|RW|0(0x00)|
|104 (0x68)|Action 4 Repeat Time|Action 4 1회 동작 시간|RW|0(0x00)|
|105 (0x69)|Action 4 Goal Speed|Action 4 Gaol Speed|RW|0(0x00)|
|106 (0x6A)|Action 4 Gal Current|Action 4 Goal Current|RW|0(0x00)|
|107 (0x6B)|Action 4 Accleration|Action 4 Acceleration|RW|0(0x00)|
|108 (0x6C)|Action 4 Delceration|Action 4 Deceleration|RW|0(0x00)|
|109 (0x6D)|Action 4 Stop|Action 4 정지 형식|RW|0(0x00)|

## 2.3 Volatile Memory(RAM)

| Address    | Name              | Description     | Access | Default       |
|:-----------|:------------------|:----------------|:-------|:--------------|
| 200 (0xC8) | Force On/Off      | 모터 출력 끄고 켜기     | RW     |       1(0x01) |
| 201 (0xC9) | Actuator Pause    | 모터 일시 정지        | RW     |       0(0x00) |
| 202 (0xCA) | Actuator Stop     | 모터 일시 정지        | RW     |       0(0x00) |
| 203 (0xCB) | LED Color         | LED On/Off      | RW     |       0(0x00) |
| 204 (0xCC) | Hardware Error    | Hardware Error  | R      |       0(0x00) |
| 205 (0xCD) | Goal Position     | 목표 위치 값         | RW     |               |
| 208 (0xD0) | Goal Speed        | 목표 속도 값         | RW     | Speed Limit   |
| 209 (0xD1) | Goal Current      | 최대 전류 값         | RW     | Current Limit |
| 210 (0xD2) | Present Position  | 현재 위치 값         | R      |               |
| 211 (0xD3) | Present Current   | 현재 소비 전류 값      | R      |               |
| 213 (0xD5) | Present Motor PWM | 모터 입력 PWM       | R      |               |
| 214 (0xD6) | Present Voltage   | 현재 전압 값         | R      |               |
| 215 (0xD7) | Moving            | 모터 동작 유무        | R      |               |
| 220 (0xDC) | Action Enable     | Action 기능 켜기/끄기 | RW     |               |
| 240 (0xF0) | Internal Data 0   | 간접 주소 0 데이터 값   |        |               |
| 241 (0xF1) | Internal Data 1   | 간접 주소 1 데이터 값   |        |               |
| 242 (0xF2) | Internal Data 2   | 간접 주소 2 데이터 값   |        |               |
| 243 (0xF3) | Internal Data 3   | 간접 주소 3 데이터 값   |        |               |
| 244 (0xF4) | Internal Data 4   | 간접 주소 4 데이터 값   |        |               |
| 245 (0xF5) | Internal Data 5   | 간접 주소 5 데이터 값   |        |               |
| 246 (0xF6) | Internal Data 6   | 간접 주소 6 데이터 값   |        |               |
| 247 (0xF7) | Internal Data 7   | 간접 주소 7 데이터 값   |        |               |
| 248 (0xF8) | Internal Data 8   | 간접 주소 8 데이터 값   |        |               |
| 249 (0xF9) | Internal Data 9   | 간접 주소 9 데이터 값   |        |               |  

## 2.4 Control Table Discription
### 2.4.1  Model Serial Number
MightyZap Model을 식별하기 위한 번호입니다.
### 2.4.2 Firmware Version  
해당 제품의 펌웨어 버전이 표기되며, Semantic Versioning 방식으로 표기합니다. 
**Semantic Versioning**
	<font color="#12bc20">major</font>.<font color="#e36c09">minor</font>.<font color="#096cec">patch</font>
	- major : 전반적인 펌웨어 개편 또는 주요 기능 수정 및 추가
	- minor : 기능 수정 및 기능이 추가된 경우
	- patch :  버그 및 코드 보완이 추가된 경우

   ![[versioning.png]]
### 4.3 Actuator ID
통신 상에서 Actuator를 식별 하기 위한 고유 번호, Daisy-chain 방식으로 연결된 Actuator들은 서로 다른 ID가 할당되어야 합니다.  
ID 값은 1~243입니다. ID 0은 Broadcase ID로 특수하게 사용 됩니다.
> <font color="#ff0000">주의사항</font>  
> 연결된 Actuator의 ID가 중복되지 않도록 주의해야 합니다. 중복된 ID가 있을 경우 통신 오류가 발생하여 정상적인 통신이 이루어지지 않습니다.  

### 4.4 Baudrate  
Actuator와 통신을 하기 위한 통신 속도 입니다.

| 설정값       | 통신 속도      |
|:----------|:-----------|
|   8(0x08) | 115200 bps |
|  16(0x10) |  57600 bps |
|  32(0x20) |  38400 bps |
|  64(0x40) |  19200 bps |
| 128(0x80) |   9600 bps |  

|Bit|Name|Description|
|---|---|---|
|Bit 7|-|미상용|
|Bit 6|Overload Error|일정 시간 이상 동안 부하가 발생한 경우|
|Bit 5|-||
|Bit 4|-||
|Bit 3|-||
|Bit 2|Motor Error|모터가 동작하지 않는 경우|
|Bit 1|Potentiometer Error|Potentiometer가 정상적으로 동작하지 않는 경우|
|Bit 0|Input Voltage Error|인가된 전압이 동작 범위를 벗어난 경우|

> **Tip**   
> Lowest input Voltage의 경우 Reset을 하지 않아도 정상 전압으로 돌아오면 정상적으로 동작이 됩니다.

### 4.6 Short/Long Stroke Limt  
위치 제어에서 목표 위치의 제한 값으로 0 ~ 10000 범위 내에서 목표 위치 값을 제한합니다.
따라서 Goal Position(203)값은 Short Stroke Limit 값보다 작을 수 없고, Long Stroke Limit 값보다 커서는 안됩니다.
![[스크린샷 2023-09-26 17-14-28.png]]
### 4.7 Start Compliance Margin  
  Start Compliance Margin은 Actuator가 Goal Position 위치 값을 지키기 위해 이동 하기 위한 위치 편차(마진)의 최소 값 입니다.  
  현재 위치(Present Position)값이 Goal Position 값보다 마진값이상 크거나 작을 경우, 위치 오차를 잡기위해 모터를 제어합니다.
  
  Start Compliance Margin은 다음의 2가지의 경우에 적용이 됩니다.  
  1. 현재 위치에서 다른 위치로 이동하기 위해 Goal Postion 값을 변경하는 경우 
```
예 1> Start Margin 이내로 Goal Position을 변경한 경우
 - Start Compliance Margin : 20
 - Present Position : 1000  
 - Goal Position : 1000 -> 1010으로 변경할 경우
 위치 편차가 10으로 마진값 보다 작아 모터는 동작 되지 않습니다.  
 
 예 2> tart Margin 보다 크게 Goal Position을 변경한 경우
 - Start Compliance Margin : 20
 - Present Position : 1000  
 - Goal Position : 1000 -> 950으로 변경할 경우
 위치 편차가50으로 마진값 보다 커 actuator는 위치 편차를 줄이기 위해 동작을 합니다. 
```

  2. 현재 위치에서 외력 또는 내부 유격에 의해 위치가 변화가 생긴 경우  
     사용자는 Goal Position을 변경하지 않았으나 Present Position이 바뀐 경우입니다.  일반적으로 외력에 의한 밀림이나 내부 유격등의 의한 현재 위치의 변동이 생길 경우 입니다.  
```
 예 1>  외부 힘에 의해 위치 편차가 발생한 겨우  
Start Compliance Margin : 20  
Goal Position : 1000  
Present Positon : 1000 -> 1010  
-> 위치 편차가 마진 값보다 적어 위치 이동이 이루어지지 않습니다.  

예 2 > 외부의 힘에 의해 위치값이 크게 변경된 경우  
Start Compliance Margin : 20  
Goal Position : 1000  
Present Positon : 1000 -> 1050  
-> 위치 편차가 마진 값보다 크게 발생하여, 위치 편차를 줄이기 위해 Actuator를 제어합니다.  
```
위의 예와 같이 Start Compliacne  Margin을 크게 설정할 경우, 외부 변화에 둔감하게 동작하여 위치 정밀도는 떨어질 수 있으나, 사용자가 제어하지(의도하지) 않은 모터의 잦은 동작을 막아 동작 안전성 및 내구성에 좋습니다.  
><font color="#ff0000">Warnning</font>  
> default로 설정된 값은 최소한의 안전성을 위해 선정된 값으로 default 값 아래로 낮추는 것은 추천 드리지 않습니다.  

### 4.8 End Compliance Margin  
End Compliance Margin은 Acuator가 정지하기 위한 최대 위치 편차 값입니다.  
Actuator가 위치 편차를 줄이기 위해 동작 중일 때 적용이 되며, Present Position과 Gaol Position과의 편차가 End Compliance Margin 보다 작을 경우 motor의 동작을 멈춥니다.  
End Compliance Margin은 작을 수록 위치 정밀도가 높아지나, 일정 값 이하로 줄일 경우 그 효과가 미미해 집니다.  

**기본 개념**
End Compliance Margin에 대한 기본적인 개념은 다음과 같습니다.
진행 방향에서의 End Complilance Marign 위치에서 Actuator 는 전기적 브레이크 명령을 내립니다. 이때 Actuator는 전기적 인 브레이크와 내부적인 마찰과 관성등에 의해 일정 거리를 이동한 후 정지하게 됩니다.  이때 이동한 정지 거리가 End Compliance Margin의 값과 동일하게 하는것이 가장 좋습니다.  
![[EndMarginBasic.gif]]  
**End Compliance 줄이기**    
부하가 적은 환경에서는 반복 정밀도를 높이기 위해 End compliance Margin을 줄이는 것이 효과적일 수 있습니다. 그렇지만 관성에 의해 밀리는 거리가 End Compliance Margin보다 길 경우 목표 위치를 벗어나 정지하게 되거나 그 이상의 거리를 이동한 후 정지 할 수 있습니다.
  ![[EnmMarginDec.gif]]
**Start Compliance Margin과 End Compliance Margin과의 관계**   
Start Compliance Margin과 End Compliance Margin과의 거리가 가깝거나 같을 경우 문제가 발생할 수 있습니다.  
<font color="#4f81bd">상황 1.  Start Margin이 End Margin이 모두 작은 경우</font>
아래의 이미지와 같이 Start Margin이 End Margin이 모두 작은 경우 부하가 크거나 관성이 있는 환경에서는 반대편  Start Margin까지 벗어나게 되는 경우가 발생하여 Over shoot 가 발생하게 됩니다.  
![[StartEndMargin.gif]]  
<font color="#4f81bd">상황 2.  Start Margin 과 End Margin이 같은 경우</font>
Start Margin 과 End Margin 거의 같고 부하가 적고 관성이 적은 제품을 제어할 경우 위치 오차와 노이즈로 아래와 같이 정상적이 정지를 못하고 진동할 수 있습니다.  
![[StartEndMargin2.gif]]

### 4.8 Acceleration/Deceration  
각각은 Actuator의 가속과 감속을 제어하는 Parameter 입니다.  
가감속 제어는 모터의 진동, 소음 부하 등을 줄이기 위한 제어 방법입니다.  Parameter에 입력된 값은 가감속 제어를 하는 기간을 의미하며 부하에 따라 제어 시간이 늘어날 수 있으며 절대적인 값은 아닙니다.  
너무 긴 시간 동안 가감속을 할 경우 제어 값이 충분하지 않아 정지한 것처럼 보일 수도 있습니다. 반대로 가속 시간이 짧을 경우 초기 동작 시 모터 또 제어 대상에 충격을 줄 수 있으며, 모터 내구성에 좋지 않습니다.  감속 시간이 짧을 경우 감속 시간이 거의 없이 최대 속도에서 정지하여 관성에 의해 이동하는 거리가 늘어나게 됩니다.  
일반적으로 감속 시간이 지나치게 짧을 경우 Overshoot가 잘 발생할 수 있습니다.   

|Parameter|Description|range|Unit|
|---|---|---|---|
|Acceleration|가속 시간|0~1000|msec|
|Deceleration|감속 시간|0~1000|msec|

![[AccDecGraph.png]]

### 4.9 Min/Max Position Calibration  
Min/Max Position Calibration Parameter는 Actuator의 Goal Position이 최소/최대 값일 때의 Rod의 위치 값을 조절하는 Parameter이다.  

|Parameter|Description|Range|Unit|
|---|---|---|---|
|Min Position Calibration|Goal Position 최소 위치 조정|0~1000||
|Max Position Calibration|Goal Position 최대 위치 조정|0~1000||

이해를 위해 아래의 이미지를 참조하여 주시기 바랍니다.  
![[minmaxPostion.png]]
- Min Poisition  
  Min Position Calibration 값을 늘릴 경우 Goal Position '0'일 때의 Min Position 위치가 늘어나게 되며 전체 동작 stroke가 줄어들게 됩니다.
  Min Position Calibration 값을 줄일 경우 Goal Position '0'일 때의 Min Position 위치가 줄어들게 되며 전체 동작 stroke가 늘어나게 됩니다. 하지만 비선형 구간이 늘어나게 됩니다.
- Max Position  
  Max Position Calibration 값을 늘릴 경우 Goal Position 최대 값일 때의 Max Position 위치가 줄어들게 되며 전체 동작 Stroke가 줄어들게 됩니다.   
  Max Position Calibration 값을 줄일 경우 Goal Position 최대 값일 때의 Max Position 위치가 줄어들게 되며 전체 동작 stroke가 늘어나게 됩니다. 하지만 비선형 구간이 늘어나게 됩니다.
  ![[minmaxCalibration.gif]]
  
### 4.10 Motor Operating Rate Limit  
Actuator의 모터를 제어하기 위해 사용되는 PWM의 최대 값 설정 Parameter 입니다.

|Parameter|Description|Range|Unit|
|---|---|---|---|
|Motor Operating Rate Limit|모터에 공급하는 PWM 의 최대 값 설정 |0~1000||

>본 가이드에서는 위치 제어 신호용 PWM과 구분하여 사용하기 위해 Motor Operating Rate 란 용어를 사용합니다.  

정격 부하 시 400 이하의 낮은 값에서는 모터가 동작하지 않을 수 있습니다.  또한 Motor Operating Rate값을 변경하면 속도와 Stall Force의 값이 변경 됩니다.  
### 4.11 Speed Limit  
Actuator의 최대 이동 속도 제한 값입니다. Speed Limit를 낮게 설정하여도 최대 Force에는 영향을 주지 않지만, 최대 전류까지 도달하는 시간은 다를 수 있습니다. 속도의 값이 낮을 수록 최대 전류까지 도달하는 시간이 길어집니다.  

|Parameter|Description|Range|Unit|
|---|---|---|---|
|Speed Limit|Actuator의 최대 속도 제한 설정 |0~1000||
Speed Limit를 변경할 경우, Goal Speed도 같이 변경됩니다. 또한 전원 인가 시 Speed Limit의 값을 Goal Speed에 적용합니다.  
Goal Speed를 변경하여도 Speed Limit는 변하지 않습니다.  
### 4.12 Current Limit  
모터 가동 중 최대 전류값을 제한 합니다. 해당 기능을 이용하여 Actuator의 최대 Force를 제한 할 수 있습니다.    
Current Limit는 비 휘발성 Parameter로 전원이 끊어져도 변경된 Data 를 유지합니다. Current Limit 값이 변경되면 Gaol Current 값도 같이 변경됩니다. 
>Current Limit/Goal current 값에 대한 동작 특성은  모터 성능 곡선 및 Datasheet를 참조하여 주시기 바랍니다.

### 4.13 Current PI Control  
모터의 전류 제어를 위한 PI Gain값입니다. 
정해진 값이 보다 큰 PI값을 적용할 경우 Goal Current와의 오차에 대해 거칠게 동작할 수 있습니다.   
정해진 값보다 작은 PI값을 적용할 경우 Goal Current와의 오차에 부드럽게 동작하나 Goal Current 값 과의 오차가 크게 나타날 수 있습니다.
>수정 시 작은 변화 값부터 적용 하신 후 테스트 해주시기 바랍니다.
>PID 값을 수정하기 전에 

### 4.14 Speed PID Control  
속도 PID 제어의 Gain 값입니다.  PID 제어에 대한 자세한 설명은 다른 문서를 참조하여 주시기 바랍니다. Gain보다 큰 값을 넣을 경우 속도 및 위치 오차에 대해 빠르게 반응하여 목표한 위치에 도달하여 정지하는 데 가지의 시간이 줄어 들게 됩니다. 
하지만, 너무 큰 Gain값을 적용할 경우  오차에 대해 거칠게 동작하여 Overshoot 도는 과도 응답 상태로 정해진 위치 값을 정지하지 못하고 모터가 진동할 수 있습니다.
또한 외란에 민감하게 반응하여 목표 값 응답이 나빠지게 됩니다.

반대로 Gain값을 적게 적용할 경우 목표 위치까지 도달하는 시간이 증가 할 수 있지만, 모터의 동작이 부드러워 질 수 있습니다. 하지만 과도하게 적은 Gain 값은 목표 위치에 도달하지 못하게 할 수도 있습니다.
PID 값을 수정하실 때는 기본 값에서 작은 값을 가 감하여 테스트 하시기 바랍니다.
<font color="#ff0000">가급적 PID값을 변경하지 마시고 가감속을 변경하여 사용하여 주시기 바랍니다.</font>
>[ 일반적인 PID값 제어 방법 ]
>![[PID_Compensation_Animated.gif]]
 [참고 문헌][https://commons.wikimedia.org/wiki/File:PID_Compensation_Animated.gif](https://commons.wikimedia.org/wiki/File:PID_Compensation_Animated.gif) 

### 4.15 Indirect Address
사용자는 해당 기능을 이용하여, 떨어져 있는 여러 Parameter를 모아서 이용할 수 있습니다.  
Indirect Address에 특정 주소를 저장하면 해당 Indirect Address는 특정 주소와 동일한 기능을 가지게 됩니다.  
예를 들어 Indirect Address 0에 '205'(Goal Position)을 쓰고, Indirect Data 0에 '5000'을 쓰면, Actuator가 '5000'의 값으로 이동을 합니다. 또한 Goal Position 값 또한 '5000'으로 변경된 것을 확인 할 수 있습니다.   
Indirect Address에 특정 주소를 세팅하면, Indirect Data에 해당 주소와 동일한 Parameter 가 됩니다.    
>Total Manager를 통해 Indricet Address 설정을 쉽게 사용할 수 있습니다.   
>사용 빈도가 높은 Parameter는 Select Box에 Option으로 추가 하였으며, 등록되지 않은 주소의 경우 'User Input' Option을 선택 하신 Select Box 옆 Test Box에 직접 작성하여 저장하여 주시면 됩니다.   
>![[indirectAddrss.gif]]

### 4.16 Extend I/O Control  
Mini 17Lf 시리즈에는 Extended I/O Port가 존재합니다. 해당 기능은 통신 4개의 I/O Port를 제공하며 , 각각은 아래와 같은 기능을 제공합니다.  
- IO Port 1 : Switch, JOG, Action Next, Action Enable, Force Off, Stop, Pause, Alarm Out, Restart 
- IO Port 2: Switch, JOG, Action Next, Action Enable,Force Off, Stop, Pause, Alarm Out, Restart  
- IO Port 3: Force Off, Stop, Pause, Action Enable, Alarm Out, Restart  
- IO Port 4 : Force Off, Stop, Pause, Action Enable, Alarm Out, Restart  
Extended I/O의 회로 구성은 각 기능에 따라 다르게 구성이 되며 외부 전원이 필요하지 않습니다.  각 기능 설명에 명시된 회로 구성대로 연결해야 Actuator 에 문제가 발생하지 않습니다.  
(connector 기구 이미지 사이드 뷰)

**Funtion Switch** 
	IO Port 1 또는 2번을 Switch 기능으로 지정 시 나머지 IO Port도 자동으로 지정 됩니다.  해당 기능은 그림과 같이 회로를 구성하였을 경우 각 버튼에 따라 short stroke Limit/Long Stroke Limit 값으로 이동을 합니다.
	(회로 구성)  
**Function JOG**
	IO Port 1 또는 2번을 Jog 기능으로 지정 시 나머지 IO Port도 작동으로 지정됩니다. 해당 기능은 그림과 같이 회로를 구성해야하며 각 버튼을 누를 경우 Short/Long 방향으로 모터가 동작 하다가 버튼을 놓았을 때 정지하게 됩니다.
**Action Enable**  
	Action Enable 기능 Action 기능을 사용할 때 사용됩니다. 
**Action Next**  
	Action Next 기능 Action 기능을 사용할 때 사용됩니다. 해당 I/O Pin에 스위치 입력이 들어와야 다음 Action 기능을 진행합니다. 자세한 내용은 4.17 Action Control을 참조하여 주시기 바랍니다.
**Force Off**  
	해당 기능은 입력 기능으로 force off 기능을 해당 I/O Port에 적용합니다. 선택한 i/o port에 스위치 회로를 연결하여 버튼을 누르면 Force On/Off toggle 기능을 수행합니다.  
**Function Stop**  
	해당 기능은 입력 기능으로 Stop 기능을 해당 I/O Port에 적용합니다. 선택한 i/o port에 스위치 회로를 연결하여 버튼을 누르면 Actuator가 정지 됩니다.  
**Function Pause** 
	해당 기능은 입력 기능으로 Pause 기능을 해당 I/O Port에 적용합니다. 선택한 i/o port에 스위치 회로를 연결하여 버튼을 누르면 Pause toggle 기능을 수행합니다.  
**Function Alarm Out**  
	해당 기능은 출력 기능으로 Hardware Error 가 발생 시 'High' 신호를 내보냅니다.  
**Restart**  
	해당 기능은 입력 기능으로 Restart 기능을 담당합니다.  Hardware Error 등의 문제로 Actuator가 정지한 경우 또는 시스템을 재 시작해야 해야하는 경우 해당 기능을 이용하여 외부에서 restart 기능을 사용할 수 있습니다.
  
### 4.17 Action Control  
Action 기능은 통신 및 외부 제어기 없이 Actuator를 제어하기 위한 방법으로 총 5개의 Action을 작성 할 수 있습니다.  
하나의 Action에는 총10개 Parameter 속성을 가지고 있으며, 크게 Action Setting, Repeat Setting, Moving Setting으로 나뉠 수 있습니다.  
(full shot 이미지)
#### Action Setting 
Action Setting은 모터가 움직이는 방식을 설정하며 아래와 같습니다.
 -  Goal Position : Action Data에 값을 >Goal Position에 입력하여 한번에 해당 위치까지 이동합니다.
 - Goal Distance : 현재 위치에서 Action Data값을 가감하여 위치 이동을 합니다. Goal Position 과 다르게 절대 위치 값이 아닌 상대적인 값으로 동작합니다.
#### Repeat Setting
반복 횟수 또는 1회 동작에 대한 동작 시간 등을 설정하는 Parameter 입니다.  
**Repeat type**
 - Interval : Repeat Time에 의해 설정된 시간 간격마다 Action을 수행합니다.  일정한 시간마다 반복된 동작이 필요할 경우 사용합니다. 
 - dWellTime : Action 명령에 의해 위치 이동이 완료된 다음 시간을 카운트 합니다.   
   위치 이동을 완료한 후 특정 시간 동안 대기해야 할 경우 사용합니다.
   <이미지 그래프로 표현>

### 4.18 Force On/Off  
Force ON/OFF를 실행 합니다. 전원이 인가 되면 자동으로 Force ON으로 설정됩니다.  

|value|동작 상태|
|---|---|
|0| 모터의 전원을 차단하여 기동력이 발생 되지 않도록 합니다.|
|1|모터의 전원을 인가하여 기동력이 발생하도록 합니다.|
### 4.19 Actuator Pause
Actuator의 일시 정지 명령으로 이동 중 Pause 명령이 내려지면, 현재 위치에서 정지하고, 현재 위치를 유지합니다. Pause 명령이 해지 되면 Goal Position 위치로 다시 이동합니다.  

|value|동작 상태|
|---|---|
|0|Goal Position 위치로 이동합니다.|
|1|모터가 일시 정지하고 현재 위치를 유지합니다.|

### 4.20 Actuator Stop
Actuator가 완전 정지하고, Goal Position 위치가 정지한 현재 위치로 변경됩니다.  
Actuator가 정지 한 후에는 자동으로 Stop Paremeter가 리셋 됩니다.  

### 4.21 LED
Error가 표시 되지 않을 때 사용자가 임의로 LED를 제어하여 디스플레이 효과를 낼 수 있습니다.  
(Error 표시가 우선)  

|bit|동작 상태|
|---|---|
|0|RED LED |
|1|GREEN LED|

### 4.22  Hardware Error
Actuator 가 동작 중 발생하는 위험 상황 중 아래의 상황에 대하여 스스로 감지하고, 다양한 방법으로 스스로를 보호할 수 있습니다.  
각  Bit들은 중복되어 설정이 되며, Alarm Shutdown, Alarm LED,  Extend IO 기능을 이용하여 Error 발생 시에 대한 조치를 할 수 있습니다.  
일반적으로 추천하는 방법은 Alarm Shutdown 기능을 이용하여 해당 Error가 발생 할 경우, Force On/Off를 '0'으로 하여,  Actuator 와  사용자의 system을 보호하는것이 좋습니다.  
ShutDown 기능을 설정하였을 경우 Restart 기능을 사용하지 않는 이상 모터가 동작하지 않습니다.  

|Bit|Name|Description|
|---|---|---|
|Bit 7|-|미상용|
|Bit 6|Overload Error|일정 시간 이상 동안 부하가 발생한 경우|
|Bit 5|-||
|Bit 4|-||
|Bit 3|-||
|Bit 2|Motor Error|모터가 동작하지 않는 경우|
|Bit 1|Potentiometer Error|Potentiometer가 정상적으로 동작하지 않는 경우|
|Bit 0|Input Voltage Error|인가된 전압이 동작 범위를 벗어난 경우|
- Overload  Error    
  2가지 방식이 있음, Motor continous current Limit 연속 전류 제한  
  Overload를 발생하는 는  I<sup>2</sup>T 방식을 이용하여 전류를 축적하여 모터를 보호하는데 사용됩니다. I<sup>2</sup>T 보호는 모터의 열 모델링을 기반으로 한 모터 과부하 보호 방법으로, 일종의 센서리스 모터 과열 보호 장치 입니다.  
  i<sup>2</sup>t = i<sub>peak</sub><sup>2</sup>t - i<sub>norm</sub><sup>2</sup>t = (i<sub>peak</sub><sup>2</sup> -i<sub>norm</sub><sup>2</sup>)t  
  아래의 그림과 같이... 이미지는 수정 및 설명 도 추가설명  
   ![[i2t_graph.png]] 
- Potentiometer Error  
  Potentiometer가 정상적인 동작을 하지 않을 때 해당 bit가 set 됩니다.  Potentiometer Error 가 지속적으로 나타날 경우 A/S가 필요함으로 당사에 문의 주시기 바랍니다.
- Input Voltage Error  
  입력 전압의 범위가 벗어날 해당 bit 가 set 됩니다. Low voltage일 경우, 다시 정상 전압으로 변경되면 해당 Error가 clear 됩니다.  
  하지만 high voltage Error 일 경우, 해당 Reset이 되지 않는 이상 해지 되지 않습니다. 
### 4.23 Goal Position
Actuator를 이동 시키고자 하는 위치 값입니다. Goal Position은 Short/Long stroke limit 설정치에 영향을 받습니다. (즉, stroke limit 범위 밖으로는 위치 명령을 내려도 stroke limit위치까지만 움직임)

### 4.24 Goal Speed
액츄에이터의 동작 속도를 변경할 때 사용합니다. [범위 : 0~ 1000]  
각 actuator의 최대 속도에 대해 비율로 제어하며 약 10%의 오차가 있습니다.
value : 0 ~ 1000 [+-10%]
![[Pasted image 20230807184527.png]]
초기 전원 인가시 비휘발성 Speed Limit에서 값을 불러와 Goal Speed에 저장합니다.
Speed Limit 명령보다 빠르게 반응하며, 가동 중 실시간으로 속도를 변경하는 데 사용할 수 있습니다.
0일 때 기동력 OFF 상태이고 1023일 때 최대 속도를 냅니다.
Goal Speed를 변경해도 Force에 영향을 주지 않습니다.
다만, 너무 낮은 값을 설정 시 모터의 반응이 늦어지거나 움직이지 못할 수 있습니다.
### 4.25 Goal Current  
모터의 최대 전류를 제한합니다. 전류 값을 제한하여 Actuator의 최대 Force를 제한 할 수 있습니다. 각 Goal Current 값에 대한 Stall Force는 Datasheet를 참조하여 주시기 바랍니다.  
초기 전원 인가시 비휘발성 Current Limit의 값을 Goal Current의 초기값으로 적용합니다.  
> **Tip** <font color="#4f81bd">Goal Current를 이용한 Force 제한</font>
> Goal Current를 조절하면 모터가 낼 수 있는 최대 힘을 조절할 수 있습니다. 제어 대상 및 사용자의 어플리케이션에 따라 특정 Force를 이상 넘어가는 것을 제한하고 자 할 때 사용하시면 됩니다.   
> 지나치게 낮은 Goal Current는 모터의 부하를 이기지 못해 동작하지 않을 수 있습니다. 
> Datasheet의 Goal Current Vs Force 표를 참조하신 후 적절한 값을 적용하시기 바랍니다. 또한 해당 값은 약 15%의 오차를 포함합니다.  

>**Warnning** <font color="#ff0000">Over Current</font>
>Goal Current 800  이상 또는 1600- 설정일 경우 모터에 무리가 발생한다. 지속적으로 사용하는 구간이 아닌 특정상황 잠시 사용하는 구간이다.  지속 적으로 사용할 경우 overload Error가 발생하거나 모터의 수명이 짧아지게 됩니다.
### 4.26 Present Postion
현재 stroke의 위치 값을 나타냅니다. 사용하고 계신 Stoke 의 최대 길이를 참조하시여 위치 값을 계산하시기 바랍니다.   
![[Pasted image 20230809113927.png]]  
정지한 이후에도 미세한 위치 변동은 나타날 수 있으며 이는 정상 동작입니다. 
### 4.27 Present Current
모터의 현재 전류 사용 값입니다.

|value|range|dfd|
|---|---|---|
|0~16000|0~1600mA|mA|
present Current는 오차를 포함하고 있음으로 참고 용으로 사용하여 주시기 바랍니다.
### 4.28 Present Motor Operating Rate
모터에 공급되는 PWM값을 나타냅니다. (통신용 PWM과의 오해를 방지하기 위해 Motor Operating Rate(모터 가동율)이라는 용어를 사용합니다. )  
Motor Operating Rate는 Goal Speed, Goal Current 등에 따라 값이 달라집니다.   
'0'은 모터가 정지한 상태를 나타냅니다.

|value|range|dfd|
|---|---|---|
|-10000~1000|0~1600mA|mA|

### 4.29 Present Voltage  
입력 전압 값을 나타 냅니다. 

|value|range|dfd|
|---|---|---|
|0~130|0~13.0|[v]|
### 4.30 Moving
모터의 동작 유무를 나타냅니다. 정확히는 모터의 목표 도달 유무를 나타냅니다.  
Motor Operating Rate 값이 '0'이어도 목표 위치 도달 완료 상태가 아니면 Moving값은 '0'이 되지 않습니다. 
### 4.31 Action Enable
Action Parameter로 작성된 Action을 실행할 때 사용합니다. Action Paramter 를 작성하였어도 Action Enable을 활성화 하지 않으면 Action은 동작하지 않습니다. 

|value|range|dfd|
|---|---|---|
|0|Action disable||
|1|Action Enable||

### 4.31 Reset
### 4.32 Restart
### 4.33 Indirect Data
indirect Address로 설정된 Paramter들의 Data를 읽고 쓸 수 있는 Parameter입니다.




