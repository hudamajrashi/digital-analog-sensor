# PIR Motion Sensor with LED (Arduino UNO)

## Project Overview

This project uses a **PIR Motion Sensor** to detect motion and control an LED.

* Motion detected → LED turns ON
* No motion → LED turns OFF

---

## What is PIR Sensor?

PIR stands for **Passive Infrared Sensor**

* Detects motion by sensing infrared radiation from objects (like humans)
* Commonly used in security systems

---

## Sensor Type

* Type: **Digital Sensor**
* Output:

  * HIGH → Motion detected
  * LOW → No motion

---

## Components Used

* Arduino UNO
* PIR Motion Sensor
* LED
* 220Ω Resistor
* Jumper Wires

---

## Circuit Connection

### PIR Sensor:

* VCC → **5V**
* GND → **GND**
* OUT → **Pin 2**

### LED:

* Long leg → **Pin 13**
* Short leg → **220Ω → GND**

---

## Circuit Diagram

![PIR Circuit](digital_sensor.png)

---

## Arduino Code

```cpp id="pircode1"
int pirPin = 2;
int ledPin = 13;

void setup() {
  pinMode(pirPin, INPUT);
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, LOW);
  Serial.begin(9600);
}

void loop() {
  int motion = digitalRead(pirPin);

  if (motion == HIGH) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }

  delay(200);
}
```

---

## How It Works

1. PIR detects motion (infrared changes)
2. Sends HIGH signal to Arduino
3. Arduino turns LED ON
4. When no motion → LOW → LED OFF

---

## Project Preview

### No Motion (LED OFF)

![No Motion](digital_sensor_off.png)

---

### Motion Detected (LED ON)

![Motion](digital_sensor_on.png)

---

## Testing

* Move your hand in front of the sensor → LED turns ON
* Stay still → LED turns OFF

---

## Applications

* Security systems
* Automatic lighting
* Motion detection alarms


