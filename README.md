🏫 2024년 2학기 피지컬 컴퓨팅 최종 프로젝트

본 프로젝트는 STM32F4 마이크로컨트롤러를 기반으로 아날로그 센서 데이터 수집, RGB LED 제어, 4자리 7세그먼트 디스플레이(FND), 인터럽트 기반 버튼 제어, 시리얼 통신(UART)을 통합한 임베디드 시스템입니다.

---

## 📌 Features

- ✅ ADC1을 활용한 아날로그 센서 데이터 수집
- ✅ USART2를 통한 시리얼 통신 (데이터 송수신)
- ✅ PWM 기반 RGB LED 제어 (TIM4 사용)
- ✅ 4자리 7세그먼트 디스플레이 출력
- ✅ 버튼(PC13) 인터럽트로 밝기 조절
- ✅ 수신 데이터에 따라 실시간 LED 색상 제어 및 숫자 표시

---

## 🛠️ Technologies

- STM32F407 Discovery Board
- STM32 HAL/LL Libraries
- C language
- Keil uVision / STM32CubeIDE

---

## 🧪 Operation

- ADC1이 주기적으로 아날로그 데이터를 수집하고 시리얼로 전송합니다.
- 수신된 데이터는 7세그먼트에 숫자로 표시됩니다.
- RGB LED는 수신값에 따라 다음과 같이 점등됩니다:
  - 60–79 → 초록
  - 80–99 → 파랑
  - 100–119 → 빨강
- 버튼(PC13)을 누를 때마다 밝기(intensity)는 ×10 배로 증가하며, 25600을 넘으면 초기화됩니다.


---

## 🧩 Pin Mapping (Major)

| Component        | Port/Pin         |
|------------------|------------------|
| RGB LED (PWM)    | PB6–PB9 (TIM4 CH1–CH4) |
| Button Input     | PC13 (EXTI)      |
| FND Segments     | PC4–PC11         |
| FND Select Lines | PB0–PB3          |
| UART TX/RX       | PA2 / PA3        |
| ADC Input        | PC0 (Channel 10) |
| Debug LED        | PA5              |
