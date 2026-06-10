# ESP32 Light Detection and Alert System

A simple embedded systems project built using an ESP32, LDR, LED, passive buzzer, and push button.

The system continuously monitors ambient light levels and automatically activates visual and audible alerts when the environment becomes dark.

## Features

* Real-time light intensity sensing using an LDR
* Automatic darkness detection
* LED indication in low-light conditions
* Audible alert using a passive buzzer
* Push-button based user interaction
* Serial Monitor output for debugging and calibration
* Adjustable threshold values for different environments

## Hardware Used

* ESP32 Dev Module
* LDR (Light Dependent Resistor)
* LED
* 220Ω Resistor
* 10kΩ Resistor
* Passive Buzzer Module
* Push Button
* Breadboard
* Jumper Wires

## Circuit Overview

### LDR Voltage Divider

3.3V → LDR → GPIO4 → 10kΩ → GND

### LED

GPIO2 → 220Ω Resistor → LED → GND

### Passive Buzzer

GPIO19 → Signal Pin

3.3V → VCC

GND → GND

### Push Button

GPIO18 → Push Button → GND

Using ESP32 internal pull-up resistor.

## Working Principle

1. The ESP32 continuously reads the analog value from the LDR.
2. A threshold value is used to determine whether the environment is bright or dark.
3. When the light intensity falls below the threshold:

   * LED turns ON
   * Passive buzzer generates an alert tone
4. When the light intensity rises above the threshold:

   * LED turns OFF
   * Buzzer stops
5. The push button can be used to control additional functionality or automation logic.

## Project Structure

```text
ESP32_Light_Detection_System/
│
├── ESP32_Light_Detection_System.ino
├── circuit_diagram.png
├── images/
│   ├── setup.jpg
│   └── working_demo.jpg
│
└── README.md
```

## What I Learned

### Sensor Interfacing

* Voltage divider circuits
* Analog sensor reading using ESP32 ADC
* Sensor calibration techniques

### Embedded Programming

* GPIO configuration
* Digital outputs
* Analog inputs
* Threshold-based decision making

### Passive Buzzer Control

A key learning from this project was understanding the difference between active and passive buzzers.

Initially, the buzzer only produced a short "tick" sound when controlled using digitalWrite(). Through experimentation and debugging, I learned that passive buzzers require a frequency signal generated using PWM or tone generation.

### Hardware Debugging

* Identifying wiring issues
* Verifying sensor readings before changing code
* Understanding signal behavior
* Testing components independently

## Challenges Faced

* Selecting suitable GPIO pins
* Calibrating light thresholds
* Identifying buzzer type
* Debugging unexpected hardware behavior
* Separating hardware issues from software issues

## Future Improvements

* MQTT integration
* Node-RED dashboard
* Cloud-based monitoring
* Mobile notifications
* Historical data logging
* Remote control and automation

## License

This project is open for learning, experimentation, and educational purposes.
