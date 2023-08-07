### Features / 주요 특장점
-  Micro size / 마이크로 사이즈
-  Precise position control/ 정밀위치제어
-  Force control by current feedback / 전류피드백 통한 포스 제어
-  Speed control (1024 resolution) / 속도제어(1024해상도)
-  Strong force comparing to the size / 체적대비 강한 힘
-  Built-in Drive Circuitry / 드라이브 회로 내장
-  RS-485 communication / RS-485 통신 지원
-  Parameter programmable on the Manager software 
  / 매니져 소프트웨어를 통한 파라메터 셋팅가능

### Common Specifications / 공통 사양
-  **Stroke / 스트로크** :27mm
-  **Rated Load / 정격 부하** : 12N~100N according to gear ratio(See appendix.) / 기어비에 따라 12~100N(별첨 참조)
   **Recommended duty cycle at rated load / 정격부하 시 권장 듀티사이클** :under 50% (50% 이하)
-  **Max applicable Load / 최대 허용 부하** : 2times rated load / 정격 부하의 2배
   **Recommended duty cycle at max applicable load / 최대 허용 부하시 권장 듀티사이클** :
   under 20% (20% 이하)
-  **Micro controller** : 32 bit ARM Core, 4096 resolution (A/D converter)
-  **Input Voltage / 입력전압**: 12.0V(Rated/정격),7V~13V(Operating)
-  **Motor Type / Watt**: coreless DC Motor / 26W
-  **Current consumption / 소모전류** : 30mA(Idle), 380mA(Rated), 1.6A(Stall)
-  **Position repeatability / 반복정밀도** :
  ⇨ Unidirectional less than 0.03mm(30um) / 단방향 0.03mm(30um)
  ⇨ Bydirectional less than +/-0.06mm(60um) / 양방향 +/-0.06mm(60um)
-  **전류값 오차 / Current Tolerance** : ±15% at Over 50mA
-  **Position sensor / 위치센서** : 10kΩ linearity potentiometer
-  **Size, Weight /크기,무게**: 57.4(L)x29.9(W)x15(H)mm / 49~52g (to be varied according to gear ratio)
-  **Communication/ 통신** : RS-485
-  **Protocol** : IR Robot Open Protocol (switchable to MODBUS RTU protocol/ MODBUS 프로토콜 전환 가능) 
-  **Operating Temperatures / 동작온도** :-10℃ ~ 60℃
-  **Ingress protection / 방수방진** : IP-54
-  **Mechanical Backlash / 기구백래쉬**: 0.03mm(30um)
-  **Audible Noise / 가청소음** : Max. 50db at 1m
-  **Gear ratio / 기어비** :10:1(12F,20F,35F) /20:1(55F) /50:1(100F)
-  **Gear type / 기어타입**: Engineering plastic gears(12F,20F,35F)
	4metal & 2engineering plastic gears(55F,100F) (Aluminum and stainless steel combination)
- **Rod type / Rod 타입** :Stainless steel rod / 스테인레스스틸
- **Standard Accessory / 표준악세서리** :1 x Hinge base, 1 x Hinge, 1 x Hinge shaft, 1 x Rod end tip, 2 x M3 NUT, 3 x M2.5x6 screws, 1 x Molex wire harness (200mm), 1 x M3 spanner, 1 x Socket set screw
- **Connector Type (Male) in the Actuator / 액츄에이터 커넥터** : MOLEX 53253-0470
- **Wire Harness** : Molex(51065-0400) to Molex(51065-0400)/ 200mm / 0.08x60(22AWG)

### Volatges / 전압

|                                    | Min    | Norm   | Max    | Unit | Note                    |
|:-----------------------------------|:-------|:-------|:-------|:-----|:------------------------|
|  **Supply voltage/ 공급전압**          |   7.0  |  12.0  |  13.0  |  V   |                         |
|  **Logic input voltage / 로직인가전압**  |  -7.0  |  -     |  12.0  |  V   |  RS-485                 |  

### Currents / 전류

|                                                                                                                                                                                                               |  Min  |  Norm            |  Max     |  Unit     |  Note                                                                                                         |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:------|:-----------------|:---------|:----------|:--------------------------------------------------------------------------------------------------------------|
|     <div>**Maximum peak Current** /&nbsp;</div><div>**최대 피크 전류**</div>                                                                                                                                        |       |    ≤1.7&nbsp;    |          |   A       |   Stall Current                                                                                               |
| **No Load Current** / **무부하전류**; |       |    ≤300          |          |   mA      |   No Load                                                                                                     |
|     <div>**Rated Load Current** /&nbsp;</div><div>**정격 부하시 전류**</div>                                                                                                                                         |       |   ≤400           |          |   mA      |   <div>at over Goal current&nbsp;</div><div>800mA setting / 골</div><div>커런트 800mA 이상</div><div>설정</div>       |
|     <div>**Max Applicable Load Current**&nbsp;</div><div>/ **최대 허용 부하시 전류**</div>                                                                                                                             |       |   ≤600           |          |           |   <div>at Goal current 1.6A&nbsp;</div><div>setting / 골커런트</div><div>1.6A설정 시</div>                           |
| **Idle Current**                                                                                                                                                                                              |       |   ≤35            |          |   mA      |                                                                                                               |  

### Temperatures / 온도

| StorageTemp. / 보관온도          | -20&nbsp; | - | 70&nbsp; | ℃ |  |
|:-----------------------------|:----------|:--|:---------|:--|:---|
| Operating Temp. / 동작온도&nbsp; |       -10 | - |       60 | ℃ |  |  

### Strokes / 스트로크

| MIN Position / 최소수축위치       |  3.3 |  3.8 |  4.3 | mm | <div>*</div><div><br></div> |
|:----------------------------|:-----|:-----|:-----|:---|:----------------------------|
| MAX Position / 최대확장위치&nbsp; | 30.3 | 30.8 | 31.3 | mm |                             |
| Stroke length/ 스트로크         | -    | 27.0 | -    | mm |                             |  
⁕: Contact us if min position of multiple actuators should be exactly same.
⁕: 복수의 액츄에이터의 최소수축위치를 완벽하게 동일하게 설정해야 하는 경우, 별도 협의

⁕매니저 소프트웨어 또는 파라메터 맵의 Min / Max Position Calibration 기능으로 Min / Max 위치값 동기화 가능.
⁕Synchronize Min / Max Position by “Min / Max Position Calibration” feature on Manager software or Parameter 
Map.

### No Load Speed / 무부하 속도

| <div>Maximum Speed at 12.0V</div><div>최대 속도 at 12.0V</div> | 100.8 | 112.0 | 123.2 | mm/s |            12Lf-12F-27 |
|:-----------------------------------------------------------|:------|:------|:------|:-----|:-----------------------|
|                                                            |  75.6 |  84.0 |  92.4 | mm/s |            12Lf-20F-27 |
|                                                            |  26.1 |  29.0 |  31.9 | mm/s | <div>12Lf-35F-27</div> |
|                                                            | 13.95 |  15.5 | 17.05 | mm/s |            12Lf-55F-27 |
|                                                            |  6.93 |   7.7 |  8.47 | mm/s |           12Lf-100F-27 |  

### Load / 부하

| Parameter                                      | Limit Values / 한계값 |        | <div>Unit</div><div>단위</div> | Remarks / 비고                          |
|:-----------------------------------------------|:-------------------|:-------|:-----------------------------|:--------------------------------------|
|                                                | Rated/정격           | Max/최대 |                              |                                       |
| <div>Load at 12.0V</div><div>부하 at 12.0V</div> |               12.0 |     24 | N                            | <div>12Lf-12F-27</div><div><br></div> |
|                                                |               2.69 |   5.39 | lbf                          |                                       |
|                                                |               1.22 |   2.44 | kgf                          |                                       |
|                                                |               20.0 |     40 | N                            |                           12Lf-20F-27 |
|                                                |               4.49 |   8.98 | lbf                          |                                       |
|                                                |               2.04 |   4.08 | kgf                          |                                       |
|                                                |               35.0 |     70 | N                            |                           12Lf-35F-27 |
|                                                |               7.87 |  15.73 | lbf                          |                                       |
|                                                |               3.57 |   7.14 | kgf                          |                                       |
|                                                |               55.0 |    110 | N                            |                           12Lf-55F-27 |
|                                                |              12.37 |  24.72 | lbf                          |                                       |
|                                                |               5.61 |  11.22 | kgf                          |                                       |
|                                                |              100.0 |    200 | N                            | <div>12Lf-100F-27</div>               |
|                                                |              22.48 |  44.94 | lbf                          |                                       |
|                                                |              10.19 |  20.40 | kgf                          |                                       |  
<p align="right"> ⁕ 1 kgf = 9.8N , 1lbf = 4.45N</p>
※ It is highly recommended to apply rated load under 50% duty cycle. When max applicable load (2times the rated load) is applied, goal current setting should be 1600 and duty cycle should be less than 20%. See Figure2-2 below.
※ 가급적 정격 부하 조건에서 사용하되, 최대 허용 부하 (정격부하의 2배) 적용시에는 Goal current설정을 1600(1.6A)으로, Duty cycle을 20% 이하로 낮추어야 합니다. 하단의 Figure2-2 그래프를 참고하십시오.

### Self Lock Feature / 셀프-락기능

|  |   | N/A(불가)&nbsp;                       | - | N | <div>12Lf-12x-27</div>                |
|:---|:--|:------------------------------------|:--|:--|:--------------------------------------|
|  | - |                                     | - | N |                           12Lf-20x-27 |
|  | - | <div>Available</div><div>(가능)</div> | - | N | <div>12Lf-35x-27</div><div><br></div> |
|  | - |                                     | - | N |                           12Lf-55x-27 |
|  | - |                                     | - | N |                          12Lf-100x-27 |  
-  Self-lock feature :The force which actuator maintains its position by mechanical friction without motor power.
- 셀프-락기능 :액츄에이터가 전원을 통한 모터의 힘 없이, 기구마찰력만으로 위치를 고수할 수 있는 힘

### Figure 1.
#### Figure1-1 . Voltage /Speed<font color="#000000">[m/s]</font> - at Goal current 1600

<font color="#ff0000">※</font> Data includes tolerance. / 해당 Data는 오차를 포함하고 있습니다.

#### Figure1-2 . Voltage /Stall Force<font color="#000000">[N]</font> - at Goal current 1600 & at Goal Speed 100

<font color="#ff0000">※ </font>Data includes tolerance. / 해당 Data는 오차를 포함하고 있습니다.

CAUTION(주의)
<font color="#ff0000">- Stall force는 참고용으로, 제품의 파손을 방지하기 위해 실제 application에서의 사용시에는 정격부하에 맞추어 사용하여 주십시오.</font>
<font color="#ff0000">- Stall force is for reference only. In order to prevent damage of the product, please use it according to the Rated load when using in actual application.</font>

### Figure 2.
#### Figure2-1 .Goal Speed /Speed<font color="#000000">[mm/s]</font> - at Goal current 800

<font color="#ff0000">※</font> Data includes tolerance. / 해당 Data는 오차를 포함하고 있습니다.

#### Figure2-2 .Goal Current / Stall Force <font color="#000000">[N]</font> - at Goal Speed 100

<font color="#ff0000">※ <font color="#ff0000">Data includes tolerance. / 해당 Data는 오차를 포함하고 있습니다.</font></font>
<font color="#ff0000">※ </font><font color="#ff0000">Data over 1200mA should be used for reference only. At currents over 1200mA, it does</font>
<font color="#ff0000">not produce a stable force. When a continuous load applied, the force gradually decreases</font>
<font color="#ff0000">and remains stable at 1A.</font>
<font color="#ff0000">※  1200mA 이상의 Data는 참고용도로만 사용하시기 바랍니다. 1200mA 이상의 전류에서는 안정적인 Force를 내지 못합니다. 지속적인 부하가 발생할 경우 Force가 점점 하락하게 되며 1A에서 안정적으로 유지됩니다.</font>

**EX) The rated & Max load for 12Lf-20x-27 (20N rated load)**

| Load       | Goal Current | Duty rate |
|:-----------|:-------------|:----------|
| 20N(Rated) |          800 | Max.50%   |
|   40N(Max) |         1600 | Max.20%   |  

**EX) The rated & Max load for 12Lf-20x-27 (20N rated load)**

|  Load              |  Goal Current  |  Duty rate  |
|:-------------------|:---------------|:------------|
|        35N(Rated)  |           800  |  Max.50%    |
|    70N(Max)&nbsp;  |          1600  |  Max.20%    |  

<font color="#ff0000">Caution / 주의</font>
본 자료는 모터의 힘을 나타낸 것으로써, 모터에 걸리는 <u>실제 부하량의 3배 정도의 힘에 해당하  Goal Current로 선정</u>하는 것을 추천합니다. 적용 부하량과 모터의 힘이 같 을 경우 모터는 움직이지 못합니다.
This data shows the stall force of the motor, and it is recommended to select a <u>goal current that corresponds to the force of about 3 times the actual load</u> on the motor. If the applied load is equal to the motor force, the motor will not move.

최고 Speed를 구현하기 위해서는 GoalCurrent값 800이상이 되어야 합니다.
In order to realize the maximum speed, the GoalCurrent value must be 800 or higher.

최대 부하량은 정격 부하량의 2배까 지만 가능하며, 2배 부하 시에는 <u>Duty rate 20%이하를 적용 해야합니다.</u>
The maximum load can be up to 2 times the rated load, and <u>under 20% duty rate</u> should be applied for 2 times the load.

#### Figure2-3 .Goal Current / Speed<font color="#000000">[m/s]</font> –Rated Load basis / 정격 부하시 기준

### Figure 3. PIN Map

| PIN NUMBER(COLOR) | PIN NAME&nbsp; | <div>FUNCTION</div> |
|:------------------:|:---------------:|:--------------------:|
|         1(YELLOW) | D-&nbsp;       | RS-485-             |
|          2(WHITE) | D+             | <div>RS-485+</div>  |
|      3(RED)&nbsp; | VCC&nbsp;      | Power +             |
|    4(BLACK)&nbsp; | GND            | Power -             |  


### Figure 4. Dimension

