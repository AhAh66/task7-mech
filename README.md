# Robot Leg Control using Arduino

##  Overview
A simple project to control a robot leg using **Arduino** and **Servo** motors. This code moves the leg forward and backward repeatedly, with the potential for expansion by adding features such as balance sensors.

## 🛠 Requirements
- **Arduino Uno** board (or any compatible board)
- 3 **Servo** motors
- **Jumper Wires**
- Suitable power source **(Battery or USB)**

## ⚙️ Wiring
| Servo Motor | Arduino Pin |
|-------------|------------|
| Hip Joint | D9 |
| Knee Joint | D10 |
| Ankle Joint | D11 |

## 🚀 Code
```cpp
#include <Servo.h>

Servo hipServo;
Servo kneeServo;
Servo ankleServo;

#define HIP_PIN 9
#define KNEE_PIN 10
#define ANKLE_PIN 11

void setup() {
  hipServo.attach(HIP_PIN);
  kneeServo.attach(KNEE_PIN);
  ankleServo.attach(ANKLE_PIN);

  hipServo.write(90);
  kneeServo.write(90);
  ankleServo.write(90);
}

void loop() {
  walkForward();
  delay(1000);
  walkBackward();
  delay(1000);
}

void walkForward() {
  hipServo.write(120);
  delay(500);
  kneeServo.write(60);
  delay(500);
  ankleServo.write(100);
  delay(500);
  resetPosition();
}

void walkBackward() {
  hipServo.write(60);
  delay(500);
  kneeServo.write(120);
  delay(500);
  ankleServo.write(80);
  delay(500);
  resetPosition();
}

void resetPosition() {
  hipServo.write(90);
  kneeServo.write(90);
  ankleServo.write(90);
  delay(500);
}
```

## 📝 How to Use
1. Connect the servo motors to the pins listed in the table above.
2. Upload the code to the **Arduino** board using **Arduino IDE**.
3. Observe the leg moving forward and backward automatically.


- Use **Inverse Kinematics** to enhance movement.
- Implement remote control via **Bluetooth or Wi-Fi**.

## 📜 License
This project is open-source and free to use with proper attribution. 😊

