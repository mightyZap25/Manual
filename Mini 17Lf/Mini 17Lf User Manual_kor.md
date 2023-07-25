> H42-020-S300-R
# 1. 주요 사양

|항목|내용|
|---|---|
|MCU|ARM CORTEX-M4 (168 [MHz], 32Bit)|
|모터|Coreless (Maxon)|
|통신속도|9,600 [bps] ~ 10.5 [Mbps]|
|동작모드|토크 제어모드  속도 제어모드  위치 제어모드  확장 위치 제어모드  PWM 제어모드(전압 제어모드)|
|무게|340 [g]|
|크기 (W x H x D)|42 x 84 x 42 [mm]|
|해상도|607,500 [pulse/rev]|
|감속비|303.75:1|
|백래쉬|< 6 [arcmin], 0.1 [°]|
|[반경방향 하중](https://emanual.robotis.com/assets/images/dxl/axial_radial_load_pro.png)|280 [N] (혼으로부터 10 [mm])|
|[축방향 하중](https://emanual.robotis.com/assets/images/dxl/axial_radial_load_pro.png)|100 [N]|
|No Load Speed|32.7 [rev/min]|
|No Load Current|0.57 [A]|
|`1` Continuous Speed|29.2 [rev/min]|
|`1` Continuous Torque|5.1 [N.m]|
|`1` Continuous Current|1.5 [A]|
|출력|20 [W]|
|동작 온도|-5 ~ +55 [°C]|
|사용 전압|24.0 [V]|
|Command Signal|디지털 패킷|
|Physical Connection|RS485 Multidrop Bus  <br>RS485 비동기 시리얼 통신 (8bit, 1stop, No Parity)|
|ID|253 ID (0 ~ 252)|
|대기 전류|30 [mA]|

`1` 명시된 토크/전류 값은 입력 모터 사양에 따른 값입니다. 일반적으로 사용하는 토크 범위는 성능 그래프를 참고하여 주시고, 장시간 사용 환경에서는 별도로 문의 바랍니다.

![](https://emanual.robotis.com/assets/images/icon_warning.png)  
**위험**  
(심각한 상해 또는 사망에 이르게 할 수 있습니다.)

- 제품 주위에 가연성 물질, 계면활성제, 음료수, 물을 분사하거나 흡입시키지 마세요.
- 작동 중인 제품에 손, 발과 같은 신체 또는 신체의 일부를 넣지 마세요.
- 제품에서 이상한 냄새가 나거나, 연기가 발생하면 전원 연결을 즉시 끊어주세요.
- 아이들이 제품으로 장난치지 않도록 하세요.
- 전원의 극성을 반드시 확인 후 배선하세요.

![](https://emanual.robotis.com/assets/images/icon_warning.png)  
**경고**  
(상해나 제품 손상의 원인이 됩니다.)

- 제품의 사용 환경을 준수하세요. (온도 : -5 ~ +55 [°C])
- 작동 중인 제품 내부로 칼날, 압정, 불씨 등을 흡입시키지 마세요.

![](https://emanual.robotis.com/assets/images/icon_warning.png)  
**주의**  
(상해나 제품 손상의 원인이 됩니다.)

- 제품을 사용자 임의로 분해 또는 개조하지 마세요.
- 제품에 강한 충격을 가하거나 떨어드리지 마세요.
## [성능 그래프](https://emanual.robotis.com/docs/kr/dxl/p/ph42-020-s300-r/#%EC%84%B1%EB%8A%A5-%EA%B7%B8%EB%9E%98%ED%94%84)[](https://emanual.robotis.com/docs/kr/dxl/p/ph42-020-s300-r/#%EC%84%B1%EB%8A%A5-%EA%B7%B8%EB%9E%98%ED%94%84)

![](https://emanual.robotis.com/assets/images/dxl/pro/h42-20-s300-r_performance_graph_2.jpg)
![[스크린샷 2023-07-17 17-42-53.png]]
**참고** : Stall torque와 Performance Graph의 최대토크의 차이는 측정 방식에 기인합니다. Stall torque는 순간적인 최대토크를 측정하는 방식으로, 고전적인 RC Servo 제품에서 주로 사용하는 사양입니다. Performance Graph는 N-T Curve라고도 불리며, 부하(load)를 점진적으로 증가시키면서 측정됩니다. 모터 구동되는 환경은 Stall torque 측정 방식보다는 Performance Graph 측정 방식에 가깝습니다. 이러한 이유로 Performance Graph가 산업전반에서 보다 폭넓게 사용됩니다. 일반적으로 Performance Graph의 최대토크는 Stall torque보다 적게 측정됩니다.

**주의** : **전원 공급시 주의사항**

- 전원이 꺼진 상태에서 장치와 전원을 연결하시고 스위치로 ON/OFF를 해주세요.
    
- 다이나믹셀 PRO 및 다이나믹셀-P의 경우 반드시 전원포트를 통해 24V 전원을 공급해주세요.
    

