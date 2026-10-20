# 🌡️ Arduino Temperature & Humidity Monitor

A simple monitor that reads temperature and humidity from a **DHT11** sensor and displays them live on a **16×2 LCD**.

---

## 🙏 Credits

This project is based on the tutorial **"Getting Started With DHT11 Temperature and Humidity Sensor : Arduino Projects For Beginners"** by **BMonster Laboratory** ([watch on YouTube](https://youtu.be/PxQruKtumvg)), with my own improvements to the reading interval and display formatting.
---

## ✨ Features

- 🌡️ Live temperature in °C (1 decimal place)
- 💧 Live humidity in %
- 🔄 Updates every 2 seconds
- ⚠️ Shows `ERROR` if the sensor reading fails

---

## 🧰 Components

| Component | Quantity |
|---|---|
| Arduino UNO | 1 |
| DHT11 temperature & humidity sensor | 1 |
| 16×2 LCD (HD44780) | 1 |
| 10kΩ potentiometer (contrast) | 1 |
| 220Ω resistor (backlight) | 1 |
| Breadboard | 1 |
| Jumper wires | As needed |

---

## 🔌 Wiring

### 16×2 LCD

| LCD pin | Connects to |
|---|---|
| VSS (1) | GND |
| VDD (2) | 5V |
| V0 (3) | Potentiometer middle leg |
| RS (4) | Pin 7 |
| RW (5) | GND |
| E (6) | Pin 8 |
| D4 (11) | Pin 9 |
| D5 (12) | Pin 10 |
| D6 (13) | Pin 11 |
| D7 (14) | Pin 12 |
| A (15) | 5V through 220Ω resistor |
| K (16) | GND |

The potentiometer's outer legs go to 5V and GND. Turn it to adjust contrast.

### DHT11 sensor

| DHT11 pin | Connects to |
|---|---|
| VCC | 5V |
| DATA | Pin 2 |
| GND | GND |

---

## 💻 Software setup

1. Install the [Arduino IDE](https://www.arduino.cc/en/software).
2. From **Library Manager**, install:
   - `DHT sensor library` by Adafruit
   - `Adafruit Unified Sensor` (required by the DHT library)
   - `LiquidCrystal` is built in.
3. Open the `.ino` file, select **Arduino UNO** and the correct port, and click **Upload**.

---

## 📟 Display

```
Temp: Humidity:
24.5C   55%
```

---

## 🧠 What I learned

- Reading digital sensors and handling failed readings with `isnan()`
- Driving a character LCD in 4-bit mode
- Adjusting LCD contrast with a potentiometer on the V0 pin
- Respecting sensor timing (the DHT11 needs about 2 seconds between readings)
