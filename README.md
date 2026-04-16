# 💧 Aqua Track - Smart Water Tank Monitoring System

Aqua Track is a complete IoT solution consisting of custom hardware and a dynamic Android application. It provides real-time monitoring of water tank levels, secure local Wi-Fi connectivity via QR code, and critical alerts to prevent tank overflow or motor dry runs.

## ✨ Features
* **Real-Time Tracking:** Accurate water depth and percentage calculations using an ultrasonic sensor with a 5-sample median filter.
* **Dynamic Neumorphic UI:** The Android dashboard automatically adapts its theme based on water levels (Red for Empty, Teal for Full).
* **Secure Access:** One-tap QR Code scanner to securely lock onto the hardware's local Wi-Fi network using token authentication.
* **Smart Alerts:** 30-second audio alarms and haptic feedback trigger automatically when the tank is Full (≥ 90%) or Empty (≤ 20%).
* **History Logging:** Built-in history tracker to review past water levels.

## 🛠️ Hardware Architecture
The physical monitoring unit acts as a standalone Access Point (SoftAP).
* **Microcontroller:** ESP8266 (NodeMCU)
* **Sensor:** JSN-SR04T Waterproof Ultrasonic Sensor
* **Tank Specs:** Calibrated for a 120cm depth with a 25cm sensor blind-spot offset.
* **Communication:** HTTP GET requests serving JSON data.

## 📱 Software Architecture
The mobile client fetches, parses, and visualizes the sensor data.
* **Platform:** Android (Java / XML)
* **Networking:** OkHttp3 for asynchronous REST API calls.
* **UI Components:** Custom Neumorphic XML drawables, MaterialCardView, and `CircularProgressBar`.
* **Tools:** Android Studio, JourneyApps Barcode Scanner.

## 🚀 Setup & Installation

### 1. Hardware (ESP8266)
1. Open the `arduino_code/aqua_track.ino` file in the Arduino IDE.
2. Install the `ESP8266WiFi` and `ESP8266WebServer` libraries.
3. Wire the JSN-SR04T sensor to the NodeMCU (TRIG to D1, ECHO to D2).
4. Flash the code to the ESP8266.

### 2. Android App
1. Open the `Aqua_Track` folder in Android Studio.
2. Sync Gradle to download OkHttp and Barcode Scanner dependencies.
3. Build and run the APK on your Android device.
4. Scan the provided QR code to connect to the tank's network and start monitoring!

## 👨‍💻 Author
**Chandra Bhushan Prajapat (PIET23CS037)**
