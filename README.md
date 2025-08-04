# esp32_RC
Controlling a robotic car wirelessly 

# 🚗 ESP32 Devkit V1 + L298N Motor Driver + Dabble (Digital Mode) - 4 Motors

This project demonstrates how to control a **simple 4-wheel robot** using  
**ESP32 Devkit V1** with an **L298N Motor Driver** through the **Dabble** mobile app in **Digital Mode (GamePad)**.

---

## 📌 Components
- ESP32 Devkit V1
- L298N Motor Driver (single module)
- 4x DC motors (connected in pairs on each channel)
- Li-ion battery or 7.4V–12V battery pack
- Jumper wires
- Dabble mobile app (Android / iOS)

---

## 🔌 Wiring

Since the L298N has only **two channels**, each channel controls **two motors in parallel**:

| ESP32 Pin | L298N Pin | Function |
|-----------|-----------|----------|
| D25       | IN1       | Right side motors - Direction 1 |
| D26       | IN2       | Right side motors - Direction 2 |
| D27       | IN3       | Left side motors - Direction 1 |
| D14       | IN4       | Left side motors - Direction 2 |
| 5V        | VCC Logic | Power for the L298N logic |
| GND       | GND       | Common ground between ESP32 and L298N |
| L298N Motor Power Input | Battery + | Main motor power supply |
| L298N Motor Power GND   | Battery - | Main motor ground |

---
RC image (![Uploading RCimage.jpg…]()
)
---

## 📲 Dabble App Setup
1. Install the **Dabble** app from Google Play or the App Store.
2. Enable **GamePad Module** in Digital Mode.
3. Pair your phone with the ESP32 via Bluetooth.
4. Use the on-screen buttons to control the car.

---

## 🛠 How It Works
- **ESP32 Devkit V1** runs the `DabbleESP32` library to receive commands from the Dabble app.
- **Digital Mode (GamePad)** sends forward, backward, left, and right commands.
- **L298N Motor Driver** controls both left and right side motors in pairs.
- ENA and ENB are directly jumpered to 5V for full-speed operation.

---

## 📚 Libraries Required
- [DabbleESP32](https://github.com/STEMpedia/DabbleESP32)

---

## ▶️ Usage
1. Upload the code to the ESP32 Devkit V1.
2. Connect the ESP32 to the L298N as per the wiring table.
3. Power the motors using an external battery connected to the L298N motor power terminals.
4. Open the Dabble app, connect to the ESP32, and start driving!

---

## ⚠️ Notes
- Each channel of the L298N drives **two motors in parallel**; both motors on the same channel will always spin in the same direction.
- Ensure your battery can provide enough current for all four motors.
- Avoid running motors directly from the ESP32 5V pin; always use a separate battery for motor power.
