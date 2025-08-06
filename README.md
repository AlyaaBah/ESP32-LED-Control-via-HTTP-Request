# ESP32 LED Control via HTTP Request

A microcontroller-based system using the ESP32 to control an onboard LED remotely via HTTP requests. The system connects to Wi-Fi and retrieves data from a server to determine whether the LED should be turned on or off. This project demonstrates principles of IoT communication, HTTP integration, and hardware-software interaction.

## Overview

This project uses an ESP32 board to fetch data from a remote server and control the built-in LED accordingly. The ESP32 connects to Wi-Fi and sends a GET request to a specified URL. Based on the response (`0` or `1`), the LED is either turned off or on. The system is designed for real-time monitoring and control using simple web-based endpoints.

- **Data retrieval URL:** `retrieve.php`  
- **Data submission URL:** `send.php`

## Features

- Wi-Fi connection using `WiFiMulti` for flexible network access  
- HTTP GET request to fetch control data from a server  
- LED control based on server response (`0` = OFF, `1` = ON)  
- Serial monitor output for debugging and status updates  
- Modular code structure for easy expansion

## Technologies Used

- **ESP32** microcontroller  
- **Arduino IDE** for development  
- **WiFi.h / HTTPClient.h** libraries for network communication  
- **Serial Monitor** for real-time feedback  
- **Web server endpoints** for data exchange

## Workflow Summary

1. ESP32 connects to Wi-Fi using predefined credentials  
2. Sends a GET request to `retrieve.php`  
3. Parses the response and converts it to an integer  
4. If the value is `1`, the LED is turned ON  
5. If the value is `0`, the LED is turned OFF  
6. Status is printed to the Serial Monitor every 5 seconds

## Challenges Faced

- **Ensuring stable Wi-Fi connection**  
  *Solution:* Used `WiFiMulti` to manage multiple access points and retry logic.

- **Parsing HTTP response correctly**  
  *Solution:* Converted response string to integer using `toInt()` and validated output.

- **Handling server errors and timeouts**  
  *Solution:* Implemented error handling using `http.errorToString()` and conditional checks.

- **Synchronizing LED state with server data**  
  *Solution:* Added delay and polling mechanism to ensure consistent updates.

## Future Enhancements

- Add POST request functionality to send sensor data to the server  
- Integrate physical button to manually override LED state  
- Add OLED display to show connection status and server response  
- Secure communication using HTTPS and token-based authentication  
- Expand to control multiple outputs (e.g., motors, relays)

---

⭐ **Created by Alyaa**


⭐ **Created by Alyaa**
