# 🚗 Autonomous Obstacle-Avoiding Vehicle

This project involves building a smart vehicle that **detects and avoids obstacles** using an **ultrasonic sensor** mounted on a **servo motor**. The logic is controlled by an **Arduino UNO**, and movement is managed via an **L298N motor driver**. The system scans its environment and makes decisions autonomously.

---

## 🔧 Components Used

| Component              | Quantity | Description                            |
|------------------------|----------|----------------------------------------|
| Arduino UNO            | 1        | Microcontroller board                  |
| L298N Motor Driver     | 1        | Dual H-Bridge motor controller         |
| HC-SR04 Ultrasonic     | 1        | Measures distance                      |
| SG90 Servo Motor       | 1        | Rotates ultrasonic sensor              |
| DC Motors + Wheels     | 2        | For vehicle movement                   |
| Chassis                | 1        | Base structure for vehicle             |
| Castor Wheel           | 1        | Self Adhesive Caster Wheel             |
| Battery Pack (7.4–12V) | 1        | Power supply                           |
| Jumper Wires           | —        | Connections                            |


---

## 📐 Circuit Diagram

**Connections Overview:**

- **Ultrasonic Sensor:**
  - Trig → A3 (Arduino)
  - Echo → A2 (Arduino)

- **Servo Motor:**
  - Signal → D11
  - VCC → 5V
  - GND → GND

- **L298N Motor Driver:**
  - IN1 (Right Motor Forward) → D3
  - IN2 (Right Motor Backward) → D2
  - IN3 (Left Motor Forward) → D5
  - IN4 (Left Motor Backward) → D4

> **Note:** ENA/ENB should be enabled using jumpers or PWM pins.

---

## 💡 Features

- Real-time obstacle detection and avoidance.
- Autonomous decision making based on distance.
- Scans left and right directions using a rotating ultrasonic sensor.
- Stops and turns based on environment.

---

## 🧠 Working Principle

1. Ultrasonic sensor scans forward.
2. If an object is detected within 20 cm, the vehicle stops.
3. Servo turns sensor to check both left and right distances.
4. The vehicle turns to the direction with more space.
5. Otherwise, it keeps moving forward.

---

## 🧾 Code

Arduino sketch is located in `obstacle_avoider.ino`.

Key functions include:

- `readDistance()` - Gets distance from HC-SR04.
- `moveForward()`, `turnLeft()`, `turnRight()` - Control movement.
- `lookLeft()`, `lookRight()` - Control servo.

---

## ⚙️ Setup Instructions

1. Assemble the circuit based on the wiring diagram.
2. Upload the Arduino code from the `.ino` file using Arduino IDE.
3. Power the setup with 7.4–12V battery.
4. Place the robot on a flat surface with obstacles ahead.
5. Observe how it navigates around them.

---

## 🧪 Testing & Calibration

- Adjust sensor angles in code if detection is too late.
- Use `Serial.print()` for debugging distances.
- Modify turning delay time for smoother response.

---

## 🔧 Troubleshooting

| Problem                      | Solution                                |
|------------------------------|-----------------------------------------|
| Motors not spinning          | Check L298N wiring and battery voltage  |
| No distance detected         | Check HC-SR04 wiring & power            |
| Servo not rotating           | Check signal pin or use separate power |
| Vehicle turns wrongly        | Invert motor pins or reverse logic      |

---

## 🚀 Future Improvements

- Add IR edge detection for cliff protection.
- Use Bluetooth or Wi-Fi for manual override.
- Add camera or ML-based image processing.
- Improve power efficiency using motor driver PWM.



##🧑‍💻About Me:
Aspiring Embedded System Developer, Drone Technology & IoT Enthusiast
**GUNI REDDY CHARAN KUMAR REDDY**  
📧 charanreddy2908@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/guni-reddy-charan-kumar-reddy-ba2414240)

