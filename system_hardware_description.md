
# Posture Pal: Real-Time Posture Monitoring System

## Overview


**Posture Pal** is a wearable posture monitoring system designed to help users maintain a healthy sitting posture. By combining multiple sensors, actuators, and a portable power source, the system can detect poor posture and alert the user to correct it in real-time.

The system consists of:

-   **2 Sensors** (Orientation & Environmental)
-   **2 Actuators** (Vibration Motor & Buzzer)
-   **1 Microcontroller** (ESP8266)
-   **1 Power Source** (LiPo Battery)

With this setup, the device monitors body orientation and environmental conditions, providing instant feedback through vibrations and sound alerts if the posture deviates from a healthy range. The LiPo battery powers the system, ensuring portability and making the device easy to wear throughout the day without needing to be plugged in.

----------

## Hardware System Description

Our system consists of the following hardware components:

### 1. BNO055 (Orientation Sensor) - Sensor 1

<img src="https://thepihut.com/cdn/shop/products/adafruit-9-dof-absolute-orientation-imu-fusion-breakout-bno055-adafruit-ada2472-28610646180035_1000x.jpg?v=1646731087" alt="BNO055 Orientation Sensor" style="width: 400px; height: auto; display: block; margin-left: auto; margin-right: auto;" />


The **BNO055** is a orientation sensor that provides highly accurate measurements of the user’s posture. It integrates a gyroscope, accelerometer, and magnetometer, and outputs the user's position in the form of Euler angles.

-   **Purpose**: Tracks the user's sitting posture by measuring the orientation of their back.
-   **How it works**: The BNO055 continuously monitors the user's position. If the user slouches or leans too far forward or backward, it triggers the actuators to alert the user.
-   **Connection**: This sensor communicates with the ESP8266 microcontroller via the I2C protocol.
----------


### 2. DHT22 (Temperature and Humidity Sensor) - Sensor 2

<img src="https://thepihut.com/cdn/shop/files/gravity-dht22-temperature-humidity-sensor-dfrobot-sen0137-40833584562371_800x.jpg?v=1693490169" alt="BNO055 Orientation Sensor" style="width: 400px; height: auto; display: block; margin-left: auto; margin-right: auto;" />

The **DHT22** is a sensor that measures both temperature and humidity. In this project, the DHT22 is used to monitor the temperature inside the wearable system, ensuring that the components (especially the battery) do not overheat and remain within safe operating limits.

-   **Purpose**: Monitors the temperature inside the wearable device to prevent overheating and ensure the components function smoothly.
-   **How it works**: The DHT22 continuously measures the temperature and humidity. If the temperature exceeds a pre-set threshold, the system triggers an alert to prevent potential damage or hazards, such as battery overheating.
-   **Connection**: The DHT22 is connected to a GPIO pin on the ESP8266 microcontroller for data communication.
----------

### 3. ESP8266 (Microcontroller)
<img src="https://thepihut.com/cdn/shop/products/assembled-adafruit-feather-huzzah-with-esp8266-with-headers-adafruit-ada3046-28610359689411_1000x.jpg?v=1646649187" alt="BNO055 Orientation Sensor" style="width: 400px; height: auto; display: block; margin-left: auto; margin-right: auto;" />


The **ESP8266** is a Wi-Fi-enabled microcontroller that serves as the brain of the system. It handles sensor data, processes the posture information, and controls the actuators when necessary.

-   **Purpose**: Collects data from both sensors, processes it, and triggers the actuators when poor posture is detected.
-   **How it works**: The ESP8266 reads orientation data from the BNO055 and environmental data from the DHT22. If poor posture is detected, it activates the actuators to alert the user.
-   **Connection**: This module is responsible for receiving sensor data via I2C and GPIO, and it drives the actuators when certain thresholds are crossed.

----------

### 4. Piezo Buzzer - Actuator 1
<img src="https://thepihut.com/cdn/shop/products/piezo-buzzer-ps1240-the-pi-hut-104255-40272443572419_800x.jpg?v=1678873479" alt="BNO055 Orientation Sensor" style="width: 400px; height: auto; display: block; margin-left: auto; margin-right: auto;" />

The **Piezo Buzzer** is a simple sound-producing device that generates a beeping sound when activated. It is used as an auditory alert to signal the user when poor posture is detected.

-   **Purpose**: Alerts the user with a sound when their posture deviates from the healthy range.
-   **How it works**: When the ESP8266 detects poor posture, it sends a signal to the buzzer to emit a sound.
-   **Connection**: The buzzer is connected to a GPIO pin on the ESP8266, which controls its activation.

----------

### 5. Vibration Motor - Actuator 2
<img src="https://thepihut.com/cdn/shop/products/vibration-motor-11-6x4-6x4-8mm-pololu-pol-2265-33118264950979_1000x.jpg?v=1646084343r" style="width: 400px; height: auto; display: block; margin-left: auto; margin-right: auto;" />
The **Vibration Motor** provides haptic feedback in the form of vibrations. When triggered, it gently vibrates to remind the user to correct their posture.

-   **Purpose**: Provides a non-intrusive way to alert the user through vibrations when poor posture is detected.
-   **How it works**: The ESP8266 sends a signal to the vibration motor when it needs to activate, providing a gentle reminder to the user to adjust their posture.
-   **Connection**: This motor is connected to the ESP8266 via a GPIO pin, similar to the buzzer.

----

### 6. LiPo Battery (Power Source)

<img src="https://thepihut.com/cdn/shop/products/2000mah-3-7v-lipo-battery-the-pi-hut-105187-39650305409219_1000x.jpg?v=1664378081" alt="LiPo Battery" style="width: 400px; height: auto; display: block; margin-left: auto; margin-right: auto;" />

The **LiPo (Lithium Polymer) Battery** provides power to the entire system, ensuring that the sensors, microcontroller, and actuators function reliably without needing a direct power connection.

-   **Purpose**: Supplies the required power to the ESP8266 and other components to maintain a portable and wearable system.
-   **How it works**: The LiPo battery stores electrical energy and supplies a steady voltage to the microcontroller and sensors, allowing the system to operate for extended periods without needing to be plugged in.
-   **Connection**: The battery is connected to the ESP8266's power input, supplying it with the necessary voltage to power all connected devices.

----------

## System Connections

The following connections are made in our system:

-   **BNO055 to ESP8266**: Connected via I2C protocol using SCL and SDA lines for data communication.
-   **DHT22 to ESP8266**: Uses a single GPIO pin for data communication.
-   **Piezo Buzzer to ESP8266**: Connected to a GPIO pin for activation when poor posture is detected.
-   **Vibration Motor to ESP8266**: Connected to another GPIO pin to trigger vibrations as an alert.
-   **LiPo Battery to ESP8266**: The LiPo battery is connected to the power pins of the ESP8266, supplying power to the entire system.

All components are mounted on a **breadboard**, and the **LiPo battery** provides portable power. The battery allows the user to wear the system for extended periods, maintaining functionality throughout the day.
