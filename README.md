# iot_based_fall_detector
A project that uses an ESP32 microcontroller and an MPU6050 sensor to detect falls and send real-time alerts to a mobile device using the Blynk.io platform.

## Features

* **Real-time Motion Tracking:** Uses an Adafruit MPU6050 library to get 3-axis accelerometer and 3-axis gyroscope data.
* **Motion-Triggered Events:** Leverages the MPU6050's built-in motion detection interrupt to efficiently identify fall-like events.
* **Cloud Notification:** Connects to the Blynk.io platform using an ESP32.
* **Instant Alerts:** Sends sensor data to the Blynk mobile app when a motion event is triggered.

## Hardware Requirements

* **ESP32** Development Board
* **MPU6050** Accelerometer/Gyroscope Module
* **Power Supply:** 7.5v Li-ion Battery and a 5v Regulator
* Jumper Wires & Breadboard

## Software & Setup

1.  **Arduino IDE:** Used to program the ESP32.
2.  **Blynk.io Account:**
    * reate a new "Template" in your Blynk account.
    * Create a "Datastream" for each virtual pin (V0-V5).
    * Set up a mobile dashboard with 6 "Value Display" widgets, linking them to V0 (AccelX), V1 (AccelY), V2 (AccelZ), V3 (GyroX), V4 (GyroY), and V5 (GyroZ)
3.  **Arduino Libraries:**
    * `BlynkSimpleEsp32.h` 
    * `Adafruit_MPU6050.h` 
    * `Adafruit_Sensor.h` 
    * `Wire.h` 

## Configuration

Before uploading the code, you must update the following definitions in your `.ino` file:

```cpp
// 1. Update Blynk Template Info
#define BLYNK_TEMPLATE_ID "YOUR_TEMPLATE_ID"
#define BLYNK_TEMPLATE_NAME "YOUR_TEMPLATE_NAME"
#define BLYNK_AUTH_TOKEN "YOUR_AUTH_TOKEN" // Get this from your Blynk project

// 2. Update your WiFi Credentials
char ssid[] = "YOUR_WIFI_SSID";
char pass[] = "YOUR_WIFI_PASSWORD";
