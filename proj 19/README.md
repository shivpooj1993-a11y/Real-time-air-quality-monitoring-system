🌍 Real-Time Air Quality Monitoring System

A real-time air quality monitoring system that collects, processes, and visualizes environmental data such as PM2.5, PM10, CO₂, temperature, and humidity.

The project includes a sensor simulation module, backend API, database, real-time dashboard, and automated testbench. The simulator allows the complete system to be demonstrated without requiring physical sensors.

📌 Project Overview

Air pollution is an important environmental concern that can affect human health and the surrounding environment. Continuous monitoring of air quality can help identify pollution levels and provide timely information to users.

This project develops a real-time air quality monitoring system that:

Generates or collects air-quality sensor readings.

Calculates an Air Quality Index (AQI).

Stores measurements in a database.

Provides REST APIs for sensor data.

Displays real-time readings on a web dashboard.

Generates alerts when pollution levels become high.

Provides historical air-quality information.

Includes a simulation and automated testbench.

🎯 Objectives

The main objectives of this project are:

Monitor air-quality parameters in real time.

Simulate sensor readings when physical hardware is unavailable.

Calculate AQI from pollutant measurements.

Store sensor data for later analysis.

Display current readings through a web dashboard.

Identify unhealthy pollution levels.

Test the system automatically using a testbench.

Provide a foundation that can later be connected to real IoT hardware.

✨ Features
Real-Time Monitoring

The system monitors:

Parameter	Description
PM2.5	Fine particulate matter
PM10	Coarse particulate matter
CO₂	Carbon dioxide concentration
Temperature	Ambient temperature
Humidity	Relative humidity
AQI	Calculated air-quality index
Dashboard

The web dashboard provides:

Current AQI

AQI category

PM2.5 reading

PM10 reading

CO₂ reading

Temperature

Humidity

Historical charts

Pollution alerts

Simulation

The project can operate without physical sensors.

The simulator generates continuously changing environmental values, allowing the complete system to be tested and demonstrated on a computer.

Simulation modes include:

Normal Mode

Polluted Mode

Random Mode

🏗️ System Architecture
                   ┌──────────────────────┐
                   │   Sensor Simulator   │
                   │                      │
                   │ PM2.5 / PM10 / CO₂   │
                   │ Temp / Humidity      │
                   └──────────┬───────────┘
                              │
                              │ HTTP / JSON
                              ▼
                   ┌──────────────────────┐
                   │    Flask Backend     │
                   │                      │
                   │ REST API             │
                   │ AQI Calculation      │
                   │ Data Validation      │
                   └──────────┬───────────┘
                              │
                 ┌────────────┴────────────┐
                 │                         │
                 ▼                         ▼
        ┌─────────────────┐      ┌──────────────────┐
        │    Database     │      │    Dashboard     │
        │                 │      │                  │
        │ Sensor Records  │      │ Live Readings    │
        │ Historical Data │      │ Charts           │
        └─────────────────┘      │ Alerts           │
                                 └──────────────────┘

🛠️ Technologies Used
Backend

Python

Flask

SQLite

REST API

Frontend

HTML5

CSS3

JavaScript

Chart.js

Testing

Python unittest

Custom sensor testbench

API testing

Simulation

Python

Randomized sensor data

HTTP requests

📁 Project Structure
real-time-air-quality-monitoring/
│
├── README.md
├── requirements.txt
├── config.py
│
├── backend/
│   ├── app.py
│   ├── database.py
│   └── aqi.py
│
├── simulator/
│   ├── sensor_simulator.py
│   └── testbench.py
│
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── tests/
│   ├── test_aqi.py
│   └── test_api.py
│
├── data/
│   └── air_quality.csv
│
└── screenshots/
    └── dashboard.png

💻 Requirements

Before running the project, install:

Python 3.9 or later

Git

A modern web browser

Optional hardware for future implementation:

ESP32

PM2.5/PM10 sensor

Temperature/humidity sensor

CO₂ sensor

The current project can be completely demonstrated using the software simulator.

⚙️ Installation
1. Clone the Repository
git clone https://github.com/YOUR-USERNAME/real-time-air-quality-monitoring.git


Navigate into the project:

cd real-time-air-quality-monitoring

2. Create a Virtual Environment

Windows:

python -m venv venv
venv\Scripts\activate


Linux/macOS:

python3 -m venv venv
source venv/bin/activate

3. Install Dependencies
pip install -r requirements.txt

▶️ Running the Project
Step 1 — Start the Backend
python backend/app.py


The backend will start on:

http://127.0.0.1:5000

Step 2 — Start the Simulator

Open another terminal and run:

python simulator/sensor_simulator.py


The simulator will generate sensor readings and send them to the backend.

Example:

Starting Air Quality Sensor Simulator...

PM2.5: 24.6 µg/m³
PM10 : 48.2 µg/m³
CO2  : 612 ppm
Temp : 27.4 °C
Humidity: 58 %

Data sent successfully.

Step 3 — Open the Dashboard

Open the frontend in your browser:

frontend/index.html


The dashboard will display the incoming sensor measurements.

🧪 Testbench

The project contains an automated testbench for validating the system.

Run:

python simulator/testbench.py


Example output:

====================================
 AIR QUALITY SYSTEM TESTBENCH
====================================

[PASS] PM2.5 range validation
[PASS] PM10 range validation
[PASS] CO2 range validation
[PASS] Temperature validation
[PASS] Humidity validation
[PASS] AQI calculation
[PASS] AQI category
[PASS] API connectivity
[PASS] Database insertion

------------------------------------
Tests Passed: 9
Tests Failed: 0
------------------------------------

TESTBENCH RESULT: PASS

🔬 Simulation Modes
Normal Mode

Simulates normal environmental conditions.

PM2.5: 10–35 µg/m³
PM10 : 20–70 µg/m³
CO₂  : 400–800 ppm

Polluted Mode

Simulates increasing pollution.

PM2.5: 80–200 µg/m³
PM10 : 150–300 µg/m³
CO₂  : 900–1800 ppm


This mode can be used to demonstrate how the system responds to deteriorating air quality.

Random Mode

Generates continuously changing readings within configured ranges.

📊 AQI

The system converts pollutant concentrations into an AQI value and assigns an air-quality category.

Example categories:

AQI Range	Category
0–50	Good
51–100	Moderate
101–150	Unhealthy for Sensitive Groups
151–200	Unhealthy
201–300	Very Unhealthy
301+	Hazardous

Note: AQI definitions and calculation methods vary by country and standard. The implementation in this project should clearly specify which AQI standard it uses rather than treating the table above as universal.

🚨 Alert System

The application can generate alerts when pollutant levels exceed configured thresholds.

Example:

⚠️ AIR QUALITY ALERT

AQI: 165
Category: Unhealthy

PM2.5: 92 µg/m³
PM10 : 181 µg/m³

High pollution detected.

🔌 API

The backend provides REST endpoints.

Get Latest Reading
GET /api/latest


Example response:

{
    "pm25": 28.4,
    "pm10": 52.7,
    "co2": 642,
    "temperature": 27.3,
    "humidity": 56,
    "aqi": 78,
    "category": "Moderate"
}

Submit Sensor Data
POST /api/readings


Example request:

{
    "pm25": 28.4,
    "pm10": 52.7,
    "co2": 642,
    "temperature": 27.3,
    "humidity": 56
}

Historical Data
GET /api/history


This endpoint returns previously recorded measurements.

🗄️ Database

The system uses SQLite to store sensor readings.

Example database record:

-----------------------------------------------------------
id | timestamp | pm25 | pm10 | co2 | temp | humidity | aqi
-----------------------------------------------------------
1  | 10:00:01  | 21.4 | 42.1 | 614 | 27.2 | 58 | 55
2  | 10:00:02  | 22.1 | 44.3 | 627 | 27.3 | 58 | 57
3  | 10:00:03  | 25.8 | 49.7 | 641 | 27.4 | 57 | 63
-----------------------------------------------------------


This historical data can be used to generate graphs and analyze pollution trends.

🧪 Testing Strategy

The testbench verifies:

Sensor values

Data types

Valid measurement ranges

AQI calculation

AQI categories

API endpoints

Database operations

Invalid input handling

Simulator-to-server communication

Run all tests using:

python -m unittest discover tests

📈 Expected Output

The dashboard should provide a view similar to:

╔══════════════════════════════════════════════╗
║       REAL-TIME AIR QUALITY MONITOR          ║
╠══════════════════════════════════════════════╣
║                                              ║
║                 AQI: 78                      ║
║                MODERATE                      ║
║                                              ║
╠══════════════╦══════════════╦════════════════╣
║ PM2.5        ║ PM10         ║ CO₂            ║
║ 28.4 µg/m³   ║ 52.7 µg/m³   ║ 642 ppm        ║
╠══════════════╩══════════════╩════════════════╣
║                                              ║
║ Temperature: 27.3 °C                         ║
║ Humidity:    56 %                            ║
║                                              ║
║          AIR QUALITY HISTORY                 ║
║                                              ║
║       📈 Real-Time Sensor Graph              ║
║                                              ║
╚══════════════════════════════════════════════╝

🔮 Future Enhancements

The project can be extended with:

ESP32 hardware integration

Real PM2.5/PM10 sensors

GPS-based monitoring

Cloud database

Mobile application

Email/SMS notifications

Machine-learning-based pollution prediction

Multiple monitoring stations

Interactive pollution maps

Weather-data integration

Automatic report generation

🎓 Academic Applications

This project can be used as an academic project for demonstrating:

Internet of Things (IoT)

Embedded systems

Python programming

REST API development

Database management

Web development

Data visualization

Software testing

Sensor simulation

Environmental monitoring

📜 License

This project is intended for educational and research purposes.

You may modify and extend the project according to your requirements.

👨‍💻 Author

Your Name

GitHub: https://github.com/YOUR-USERNAME

Project: Real-Time Air Quality Monitoring System

⭐ Acknowledgement

This project demonstrates how sensor data, software simulation, backend services, databases, and web visualization can be combined to create a real-time environmental monitoring system.