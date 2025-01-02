# ESP32-DATALOGGER

## Overview

This repository contains the design and implementation details of three dataloggers based on the ESP32, ESP32-S3, and ESP32-S3 platforms. These devices are equipped with various peripherals and communication protocols to serve as versatile solutions for data acquisition and logging applications.

---

## Features

### Microcontroller Platforms:
1. **ESP32**
2. **ESP32-S3**
3. **ESP32-S3 with Advanced Peripherals**

### Peripherals:
- **I2C Devices:**
  - **MPU6050**: Accelerometer and Gyroscope for motion sensing.
  - **OLED Display**: For visual feedback and data visualization.
  - **BME680**: Environmental sensor for temperature, humidity, pressure, and air quality.

- **Communication Interfaces:**
  - **RS485**: For long-distance, reliable industrial communication.
  - **CAN (Controller Area Network)**: For automotive and robust communication.
  - **RS232**: Standard serial communication for various legacy devices.

- **Data Storage:**
  - **SD Card**: Local storage for data logging.

### Power Supplies:
- **230V AC to 5V DC**: Converts mains power for the device.
- **5V DC to 3.3V DC**: Supplies power to the ESP32 and low-voltage peripherals.
- **5V DC to 5V DC (Isolated)**: Provides isolated power for communication devices like RS485 and CAN.

---

## Hardware Architecture

### Block Diagram:
```text
  Mains Power (230V AC) → [230V to 5V Converter] → [5V Bus]
                                        ↘→ [5V to 3.3V Converter] → ESP32 / Peripherals
                                        ↘→ [5V to 5V Isolated Converter] → RS485 / CAN
```

### Communication Interfaces:
- **RS485, RS232, and CAN**:
  - Ensure robust and reliable communication.
  - Isolation is used to prevent electrical interference.

### Sensors and Peripherals:
- **MPU6050**: Used for motion-based applications like tilt sensing or vibration analysis.
- **OLED**: Displays real-time data or system status.
- **BME680**: Environmental monitoring for applications like weather stations or air quality measurement.

---

## Software Features

### Data Logging
- Logs data from MPU6050, BME680, and other connected sensors.
- Saves logs in CSV format on the SD card for easy analysis.

### Communication Protocols
- Transmits and receives data using RS485, RS232, and CAN interfaces.
- Configurable baud rates and communication parameters.
- Saves logs in CSV format on the SD card for easy analysis.

### OLED Display
- Displays sensor readings, status, and diagnostic information.

### Power Management
- Efficient power regulation with isolated supplies for sensitive peripherals.
- Compatible with industrial-grade power requirements.

---

## Getting Started

### Prerequisites
- Install [ESP-IDF](https://github.com/espressif/esp-idf) or [Arduino IDE](https://www.arduino.cc/) for programming the ESP32.
- Required libraries:
  - **MPU6050**: [`Adafruit_MPU6050`](https://github.com/adafruit/Adafruit_MPU6050).
  - **BME680**: [`Adafruit_BME680`](https://github.com/adafruit/Adafruit_BME680).
  - **OLED**: [`Adafruit_SSD1306`](https://github.com/adafruit/Adafruit_SSD1306).
  - **RS485, RS232, CAN**: Use drivers from ESP-IDF or third-party libraries.

### Hardware Setup
1. **Connect I2C Devices**:
   - MPU6050: Connect `SDA` and `SCL` to the respective GPIO pins.
   - OLED: Same as above, with separate I2C address.
   - BME680: Same bus as MPU6050.

2. **Set Up Communication Interfaces**:
   - RS485 and CAN require external transceivers.
   - RS232 uses UART GPIO pins.

3. **Power Supply**:
   - Use the 230V AC to 5V DC converter to power the system.
   - Ensure isolation for RS485 and CAN with the isolated 5V DC converter.

4. **Insert SD Card**:
   - Use a standard SD card formatted with FAT32.

### Hardware Design with KiCAD 8.0
Schematic and PCB Design

The schematics and PCB designs for the dataloggers are created using KiCAD 8.0. You can open the designs directly in KiCAD 8.0 to view, edit, or export them.
Opening the Project in KiCAD 8.0

-    Install KiCAD 8.0.
    Clone the repository:

    git clone https://github.com/your-repo/esp32-datalogger.git
    cd esp32-datalogger

-    Open KiCAD 8.0 and navigate to the project directory.
-   Open the .kicad_pro file to load the project.
    Use the Schematic Editor to view or modify the circuit schematic.
-    Use the PCB Editor to view or modify the PCB layout.



---

## Usage
1. Power on the device.
2. View real-time data on the OLED display.
3. Access logged data from the SD card.
4. Use RS485, RS232, or CAN for remote communication.

---

## Applications
- Environmental monitoring.
- Motion analysis.
- Industrial data acquisition.
- Communication gateways.

---

## Troubleshooting
1. **No Display on OLED**:
   - Check I2C connections and addresses.
2. **No Data on SD Card**:
   - Verify SD card format and connection.
3. **Communication Issues**:
   - Check baud rates and wiring for RS485/RS232/CAN.

---

## Contributing
Feel free to fork the repository and contribute via pull requests. Ensure changes are well-documented.

---

## License
This project is licensed under the MIT License. See `LICENSE` for details.

---