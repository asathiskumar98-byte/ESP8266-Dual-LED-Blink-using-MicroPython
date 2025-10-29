# 🔆 ESP8266 Dual LED Blink using MicroPython

This project demonstrates how to blink **two LEDs** alternately using an **ESP8266** microcontroller programmed with **MicroPython**.  
It’s a beginner-friendly example for testing GPIO outputs and understanding basic timing control using the **Thonny IDE**.

---

## 🧠 Project Overview

| Component | Description |
|------------|-------------|
| **Board** | ESP8266 |
| **IDE** | Thonny IDE |
| **Language** | MicroPython |
| **USB Driver** | Silicon Labs CP210x USB to UART Bridge |
| **LED1 Pin** | GPIO16 |
| **LED2 Pin** | GPIO2 |

---

## ⚙️ Requirements

- ESP8266 board (NodeMCU or compatible)
- 2 LEDs + 2 × 220Ω resistors
- Micro USB cable
- [Thonny IDE](https://thonny.org/)
- [Silicon Labs CP210x USB Driver](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)
- MicroPython firmware installed on ESP8266

---

## 🧩 Circuit Connections

| ESP8266 Pin | Component | Description |
|--------------|------------|--------------|
| GPIO16 | LED1 | Active Low |
| GPIO2 | LED2 | Active Low |
| GND | Both LEDs | Common Ground |

💡 **Tip:** Connect the shorter LED leg (–) to **GND** through a resistor.

---

## 💻 Code

```python
# GPIO2 = LED1
# GPIO16 = LED2

import machine
import utime

led1 = machine.Pin(16, machine.Pin.OUT)
led2 = machine.Pin(2, machine.Pin.OUT)

while True:
    led1.value(0)
    led2.value(1)
    utime.sleep_ms(500)
    led1.value(1)
    led2.value(0)
    utime.sleep_ms(500)
