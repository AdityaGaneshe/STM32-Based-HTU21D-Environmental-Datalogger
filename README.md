# STM32-Based HTU21D Data Logger Using Interrupt-Driven UART Communication

## 📌 Project Overview

This project implements a real-time environmental data logging system using the **STM32F411RE microcontroller** and the **HTU21D temperature and humidity sensor**. It uses I2C communication to acquire sensor data and interrupt-driven UART communication to transmit readings to a serial terminal.

The project demonstrates embedded systems programming, peripheral configuration, interrupt handling, and real-time sensor data acquisition using STM32CubeIDE.

## 🎯 Objectives

- Acquire real-time temperature and humidity data from the HTU21D sensor.
- Implement I2C communication between the sensor and STM32 microcontroller.
- Transmit sensor readings using interrupt-driven UART communication.
- Accept user commands through UART receive interrupts.
- Demonstrate non-blocking serial communication for efficient CPU utilization.

## 🛠️ Hardware Requirements

- STM32 NUCLEO-F411RE Development Board
- HTU21D Temperature and Humidity Sensor
- USB Cable
- Jumper Wires
- Computer with STM32CubeIDE

## 💻 Software and Technologies

- **Programming Language:** Embedded C
- **IDE:** STM32CubeIDE
- **Configuration Tool:** STM32CubeMX
- **Microcontroller:** STM32F411RE
- **Communication Protocols:** I2C and UART
- **Firmware Library:** STM32 HAL (Hardware Abstraction Layer)

## 🔌 Hardware Connections

| HTU21D Sensor | STM32F411RE |
|---|---|
| SDA | PB7 (I2C1 SDA) |
| SCL | PB6 (I2C1 SCL) |
| VCC | Sensor-compatible supply |
| GND | GND |

### UART Configuration

| Parameter | Configuration |
|---|---|
| Peripheral | USART2 |
| TX | PA2 |
| RX | PA3 |
| System Clock | 84 MHz |
| Status LED | PA5 |

## ⚙️ Working Principle

1. **Sensor Initialization:** The STM32 microcontroller initializes the I2C and UART peripherals.
2. **Data Acquisition:** The HTU21D sensor provides raw temperature and humidity readings over I2C.
3. **Data Conversion:** Raw sensor values are converted into temperature in Celsius and relative humidity percentages.
4. **UART Transmission:** Sensor readings are transmitted to the serial terminal using interrupt-driven UART communication.
5. **Command Processing:** UART receive interrupts allow users to control logging through serial commands.
6. **Real-Time Monitoring:** Temperature and humidity values are continuously monitored and displayed on the terminal.

## ⌨️ UART Commands

| Command | Function |
|---|---|
| `1` | Start data logging |
| `0` | Stop data logging |
| `R` | Request an immediate sensor reading |

## 📐 Sensor Conversion Formulas

**Temperature (°C):**

`T = -46.85 + (175.72 × S_T / 65536)`

**Relative Humidity (%):**

`RH = -6 + (125 × S_RH / 65536)`

Where `S_T` and `S_RH` represent the raw temperature and humidity sensor readings, respectively.

## 📊 Results

The project demonstrated successful environmental data acquisition and interrupt-driven UART communication.

- **Temperature:** Approximately 35.40°C–35.44°C under the reported laboratory conditions.
- **Relative Humidity:** Approximately 32.53%–32.72%.
- **On-Demand Reading:** The `R` command triggered an immediate sensor reading.
- **Start/Stop Control:** UART commands enabled logging control.
- **Interrupt-Driven Communication:** UART transmission and reception operated through interrupt callbacks instead of continuous polling.

*Note: Readings may vary depending on environmental conditions, sensor handling, and hardware setup.*

## 🧠 Key Concepts Learned

- STM32 microcontroller programming
- I2C sensor interfacing
- UART serial communication
- Interrupt-driven embedded systems
- STM32 HAL library
- Peripheral configuration using STM32CubeMX
- Real-time environmental monitoring
- Embedded firmware development and debugging

## 🚀 Future Improvements

- Implement I2C communication using DMA or interrupts for more complete non-blocking operation.
- Add SD card or external memory support for persistent data logging.
- Develop a graphical dashboard for real-time sensor visualization.
- Add wireless connectivity for remote environmental monitoring.
- Integrate the system with an Edge AI platform for intelligent environmental analysis.

## 👨‍💻 Contributors

- **Aditya Ganeshe**
- Parth Dobhada
- Pranav Karande

## 📚 Project Information

- **Course:** Embedded Edge AI (2307313L)
- **Academic Year:** 2025–2026
- **Platform:** STM32 NUCLEO-F411RE

---

⭐ If you find this project useful, consider giving this repository a star!
