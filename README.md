# ESP32 RFID Automated Attendance System

An end-to-end embedded IoT system that reads MFRC522 RFID tags, renders live telemetry onto an SSD1306 OLED screen, and transmits event payloads via HTTP POST webhooks to an n8n workflow engine for automated attendance logging.

## Technical Architecture
* **Hardware Interfacing:** MFRC522 RFID module over **SPI** and SSD1306 OLED display over **I2C**.
* **Microcontroller Firmware:** ESP32 handling asynchronous Wi-Fi reconnect routines and JSON payload construction via ArduinoJson.
* **Automation Backend:** n8n workflow engine deployed on Render, processing webhook payloads into persistent logs and external alerts.

## Pinout Mapping
| Component | ESP32 Pin | Protocol / Function |
| :--- | :--- | :--- |
| MFRC522 SS | GPIO 5 | SPI CS |
| MFRC522 RST | GPIO 27 | Reset |
| MFRC522 SCK | GPIO 18 | SPI Clock |
| MFRC522 MISO | GPIO 19 | SPI MISO |
| MFRC522 MOSI | GPIO 23 | SPI MOSI |
| SSD1306 SDA | GPIO 21 | I2C SDA |
| SSD1306 SCL | GPIO 22 | I2C SCL |
| Buzzer | GPIO 4 | Audio Feedback |
| Onboard LED | GPIO 2 | Visual Feedback |
