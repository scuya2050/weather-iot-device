# Weather IoT Device

This repository serves as the **coordinator for the complete Weather IoT Device**, which is composed of two independent but interconnected microcontroller projects:

- [`weather-iot-sensor`](https://github.com/scuya2050/weather-iot-sensor): Gathers environmental data using sensors.
- [`weather-iot-wifi`](https://github.com/scuya2050/weather-iot-wifi): Receives sensor data and transmits it via Wi-Fi to the cloud.

Together, they form a modular system for environmental monitoring and cloud integration.

Specifics for the components of the device can be found in their respective projects

## Device Setup


**Front**

![Device: Front](https://drive.google.com/uc?id=1x0ZgXlI--nRVUkQLewNJfkuE9jZQESTZ)



**Back**

![Device: Back](https://drive.google.com/uc?id=14ejcVIHO6SrFkeD85URkMfdWWA8HiSIC)

Specifics for the components of the device can be found in the [`weather-iot-sensor`](https://github.com/scuya2050/weather-iot-sensor) (Arduino Nano) and [`weather-iot-wifi`](https://github.com/scuya2050/weather-iot-wifi) (ESP32-01S) projects for each sub-device.

To stablish the UART connections between the sub-devices, instead of directly connecting the TX/RX ends of each, a workaround setup was performed by using Schottky diodes, since initially each sub-device would posses it's own independend power source and the workaround would prevent leaking or parasitic currents when just one sub-device was on. Please refer to the following link that was used as inspiration:

 https://electronics.stackexchange.com/questions/356043/how-does-input-pin-voltage-protection-with-schottky-work

## How it works

1. `weather-iot-sensor` reads data from temperature, humidity, and pressure sensors.
2. It sends that data via UART to the `weather-iot-wifi` module.
3. The Wi-Fi module formats the data and sends it to a cloud service or API endpoint (e.g., AWS, S3).
4. This data is later consumed in the broader data pipeline.

**Demo**

[![Watch the demo](https://drive.google.com/uc?id=1ynL5ZIdr5Dtjvxb-9NPG-Xl9nS5MYr3V)](https://drive.google.com/file/d/17TZ3vrrcig424YB1HIAV1cwt8I9Ifuxn/view?usp=sharing)


## Getting Started

### 1. Clone the repository and initialize submodules

```bash
git clone --recurse-submodules https://github.com/scuya2050/weather-iot-device.git
cd weather-iot-device
```

Or, if already cloned:

```bash
git submodule update --init --recursive
```

### 2. Open Projects in PlatformIO

Open each project (`weather-iot-sensor`, `weather-iot-wifi`) separately in VSCode with PlatformIO installed.

## Project Structure

```
weather-iot-device/
├── weather-iot-sensor/      # Submodule: Sensor microcontroller project
├── weather-iot-wifi/        # Submodule: Wi-Fi microcontroller project
├── media/                   # Images and videos of the complete device
└── README.md
```