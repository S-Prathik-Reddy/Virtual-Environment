# 🌡️ IoT Sensor Data Simulator using ThingSpeak

This project simulates an IoT device that periodically sends **temperature**, **humidity**, and **CO₂ levels** to a [ThingSpeak](https://thingspeak.com/) channel using Python. It's ideal for demonstrating cloud-based IoT systems without needing physical sensors.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
  - [1. Prerequisites](#1-prerequisites)
  - [2. Installation](#2-installation)
  - [3. Configuration](#3-configuration)
  - [4. Running the Simulation](#4-running-the-simulation)
- [How It Works](#-how-it-works)
- [Example Output](#-example-output)
- [Visuals](#-visuals)
- [Customization Ideas](#-customization-ideas)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 📖 Overview

This Python script emulates a virtual IoT device that sends synthetic sensor data to ThingSpeak every 30 seconds. It includes three key parameters:
- 🌡️ Temperature (in °C)
- 💧 Humidity (in %)
- 🌫️ CO₂ concentration (in ppm)

You can use this for:
- Testing ThingSpeak or similar cloud platforms
- Demonstrating IoT workflows
- Educational and academic use cases

---

## ✨ Features

- 🔁 Automatic data generation every 30 seconds
- ✅ Realistic random values for sensor readings
- ☁️ Sends data via HTTP POST to ThingSpeak
- 💬 Console logging of sent data and server responses
- 🛠️ Easy to customize or extend with real sensors

---

## 📁 Project Structure

```
iot-thingspeak-simulator/
├── main.py          # Python script to simulate sensor data
└── README.md        # Project documentation
```

---

## 🚀 Getting Started

### 1. Prerequisites

- Python 3.7 or newer
- A ThingSpeak account with an active channel and Write API Key

### 2. Installation

Clone the repository and install required packages:

```bash
git clone https://github.com/your-username/iot-thingspeak-simulator.git
cd iot-thingspeak-simulator
pip install requests
```

### 3. Configuration

Open `main.py` and replace the placeholder API key:

```python
write_api_key = "YOUR_THINGSPEAK_WRITE_API_KEY"
```

Ensure your ThingSpeak channel has 3 fields:
- Field 1: Temperature
- Field 2: Humidity
- Field 3: CO₂

### 4. Running the Simulation

To start sending data:

```bash
python main.py
```

---

## ⚙️ How It Works

The script:
1. Generates a random temperature, humidity, and CO₂ value.
2. Sends a POST request to ThingSpeak with these values.
3. Waits for 30 seconds, then repeats.

Here’s a quick code snippet:

```python
temperature = round(random.uniform(-50, 50), 2)
humidity = round(random.uniform(0, 100), 2)
co2 = round(random.uniform(300, 2000), 2)

response = requests.post(channel_url, params={
    'api_key': write_api_key,
    'field1': temperature,
    'field2': humidity,
    'field3': co2
})
```

---

## 💻 Example Output

```
Posted: 21.56 48.7 638.2 | Response: 201
Posted: -12.44 97.2 1845.6 | Response: 202
```

You’ll see updates every 30 seconds with the sensor values and ThingSpeak’s response ID.

---

## 🖼️ Visuals

Once configured, your ThingSpeak dashboard will show real-time charts like:

- 📊 Temperature vs Time
- 💦 Humidity trends
- 🌫️ CO₂ concentration levels

You can customize the dashboard layout and visualization styles on ThingSpeak.

---

## 🛠️ Customization Ideas

- Connect to real sensors using Raspberry Pi or Arduino
- Use MQTT protocol instead of HTTP
- Add error handling and retry logic
- Store backups in a local CSV file
- Add timestamps and device metadata

---



## 👨‍💻 Author

Prathik Reddy sannapureddy 

---

