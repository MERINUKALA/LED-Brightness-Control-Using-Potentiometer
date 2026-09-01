# 💡 Controlling LED Brightness Using Potentiometer & Arduino

An **Embedded Systems project** that demonstrates real-time LED brightness control using a **potentiometer and Arduino UNO**. The potentiometer provides an analog input, which is read by the Arduino and converted into a corresponding **PWM signal** to control the brightness of the LED.

## 📌 Project Overview

This project demonstrates how an Arduino can read an analog signal from a potentiometer and use **Pulse Width Modulation (PWM)** to increase or decrease LED brightness.

By rotating the potentiometer:

* 🔄 Clockwise → LED brightness increases
* 🔄 Counterclockwise → LED brightness decreases

This project is useful for understanding **analog input, ADC, PWM, and duty cycle** concepts in embedded systems.

## ⚙️ Working Principle

```text
       Potentiometer
             ↓
      Analog Input (A0)
             ↓
        Arduino UNO
             ↓
       PWM Processing
             ↓
       PWM Output Pin
             ↓
            LED
             ↓
   Variable Brightness
```

## 🔧 Components Required

| Component            |    Quantity |
| -------------------- | ----------: |
| Arduino UNO          |           1 |
| Potentiometer (10KΩ) |           1 |
| LED                  |           1 |
| Resistor (220Ω)      |           1 |
| Breadboard           |           1 |
| Jumper Wires         | As required |

## 🔌 Circuit Connections

### Potentiometer

| Potentiometer Pin | Arduino UNO |
| ----------------- | ----------- |
| Left Pin          | 5V          |
| Middle Pin        | A0          |
| Right Pin         | GND         |

### LED

| LED Pin     | Arduino UNO                     |
| ----------- | ------------------------------- |
| Anode (+)   | PWM Pin 9 through 220Ω resistor |
| Cathode (-) | GND                             |

> **Note:** The LED must be connected through a suitable current-limiting resistor.

## 🧠 How It Works

The Arduino's **ADC (Analog-to-Digital Converter)** reads the potentiometer voltage as a value between **0 and 1023**.

The Arduino then maps this value to the PWM range of **0 to 255**.

```text
Potentiometer
     ↓
Analog Value: 0 – 1023
     ↓
     map()
     ↓
PWM Value: 0 – 255
     ↓
LED Brightness
```

### PWM Relationship

* **0% Duty Cycle** → LED OFF
* **50% Duty Cycle** → Medium Brightness
* **100% Duty Cycle** → Maximum Brightness

## 💻 Arduino Code

```cpp
const int potPin = A0;
const int ledPin = 9;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  int potValue = analogRead(potPin);

  int brightness = map(potValue, 0, 1023, 0, 255);

  analogWrite(ledPin, brightness);

  delay(10);
}
```

## 📊 Input and Output

| Potentiometer Position | Analog Reading | PWM Output | LED Brightness |
| ---------------------- | -------------: | ---------: | -------------- |
| Minimum                |              0 |          0 | OFF            |
| Low                    |           ~255 |        ~64 | Low            |
| Middle                 |           ~512 |       ~128 | Medium         |
| High                   |           ~768 |       ~191 | High           |
| Maximum                |           1023 |        255 | Maximum        |

## 🎯 Key Concepts Learned

* ✅ Analog Input
* ✅ ADC (Analog-to-Digital Conversion)
* ✅ PWM (Pulse Width Modulation)
* ✅ Duty Cycle
* ✅ Arduino Programming
* ✅ LED Control
* ✅ Potentiometer Interfacing
* ✅ Hardware–Software Integration
* ✅ Real-time Embedded Control

## 🌍 Applications

This basic concept can be extended to:

* 💡 Automatic lighting systems
* 🏠 Home automation
* 🚗 Vehicle dashboard lighting
* 🖥️ Display brightness control
* 🔌 Power control systems
* 🤖 Robotics projects
* 🌐 IoT-based lighting systems

## 🚀 Future Improvements

* Add an **LDR sensor** for automatic brightness control.
* Replace the potentiometer with a **light sensor**.
* Add an **OLED/LCD display** to show brightness percentage.
* Control multiple LEDs independently.
* Implement IoT-based remote brightness control using **ESP8266/ESP32**.

## 📁 Project Structure

```text
LED-Brightness-Control/
│
├── LED_Brightness_Control.ino
├── README.md
└── images/
    ├── circuit.jpg
    └── output.jpg
```

## 📸 Project Demonstration

Add your project images or demonstration video here:

```markdown
![Circuit Setup](images/circuit.jpg)

![Project Output](images/output.jpg)
```

## 👩‍💻 Author

**Meri Nukala**

🎓 Electronics & Communication Engineering Student

🔗 LinkedIn: https://www.linkedin.com/in/meri-nukala-819957306


