# Weather IoT Device

This repository serves as the **coordinator for the complete Weather IoT Device**, which is composed of two independent but interconnected microcontroller projects:

- [`weather-iot-sensor`](https://github.com/scuya2050/weather-iot-sensor): Gathers environmental data using sensors.
- [`weather-iot-wifi`](https://github.com/scuya2050/weather-iot-wifi): Receives sensor data and transmits it via Wi-Fi to the cloud.

Together, they form a modular system for environmental monitoring and cloud integration.

## Images

> _Place images of the assembled device and setup here._

**Placeholder 1: Full Device Setup**
```
![Full device setup](media/device-full.jpg)
```

**Placeholder 2: Sensor Module Close-up**
```
![Sensor module](media/sensor-module.jpg)
```

**Placeholder 3: Wi-Fi Receiver Close-up**
```
![Wi-Fi module](media/wifi-module.jpg)
```

## Demo Video

> _Embed a video showing the device in action._

**Placeholder: Video Demo**
```
[![Watch the demo](media/demo-thumbnail.jpg)](https://link-to-your-video.com)
```

## How It Works

1. `weather-iot-sensor` reads data from temperature, humidity, and pressure sensors.
2. It sends that data via UART to the `weather-iot-wifi` module.
3. The Wi-Fi module formats the data and sends it to a cloud service or API endpoint (e.g., AWS, S3).
4. This data is later consumed in the broader data pipeline.

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

--

## Project Structure

```
weather-iot-device/
├── weather-iot-sensor/      # Submodule: Sensor microcontroller project
├── weather-iot-wifi/        # Submodule: Wi-Fi microcontroller project
├── media/                   # Images and videos of the complete device
└── README.md
```