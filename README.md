# IoT-ML Environmental Monitoring System

An IoT-based environmental monitoring system designed to collect, analyze, and predict air quality and environmental conditions using sensor devices and machine learning.

The project combines **embedded systems, IoT, data processing, machine learning, and backend technologies** to provide continuous environmental monitoring and predictive analysis.

## Overview

The system collects environmental data from a custom IoT device equipped with multiple sensors. The collected measurements are transmitted to a backend service, where they can be stored, processed, visualized, and analyzed using machine learning models.

The main goal of the project is to develop a system capable of:

* monitoring air quality in real time;
* collecting environmental sensor data;
* detecting changes and abnormal measurements;
* analyzing historical environmental data;
* predicting future sensor values;
* providing data through a web-based interface.

## System Architecture

```text
┌──────────────────────────────┐
│        IoT Device            │
│                              │
│          ESP32               │
│     ┌────┬────┬────┐         │
│     │BME │SCD │SPS │         │
│     │680 │ 41 │ 30 │         │
│     └────┴────┴────┘         │
└──────────────┬───────────────┘
               │
               │ Sensor Data
               ▼
┌──────────────────────────────┐
│         Backend              │
│                              │
│   Data Collection / API      │
│   Data Processing            │
│   Database                   │
└──────────────┬───────────────┘
               │
        ┌──────┴──────┐
        │             │
        ▼             ▼
┌──────────────┐ ┌──────────────┐
│ Visualization│ │ ML Pipeline  │
│              │ │              │
│    React     │ │ Python/ML    │
└──────────────┘ └──────┬───────┘
                        │
                        ▼
                 ┌─────────────┐
                 │ Predictions │
                 └─────────────┘
```

## Hardware

The prototype is based on an **ESP32** microcontroller and environmental sensors.

### ESP32

ESP32 is used as the main controller of the IoT device. It is responsible for:

* communicating with sensors;
* collecting measurements;
* preprocessing sensor data;
* connecting to the network;
* transmitting data to the backend.

### BME680

Measures environmental parameters such as:

* temperature;
* humidity;
* atmospheric pressure;
* gas resistance.

### SCD41

A photoacoustic CO₂ sensor used for measuring:

* CO₂ concentration;
* temperature;
* relative humidity.

### SPS30

A particulate matter sensor used to measure fine particles, including:

* PM1.0;
* PM2.5;
* PM4.0;
* PM10.

## Machine Learning

Machine learning is used to analyze historical environmental measurements and identify patterns in sensor data.

The ML component can be used for:

* time-series forecasting;
* environmental condition evaluation;
* anomaly detection;
* analysis of relationships between sensor parameters;
* prediction of future air-quality indicators.

The general ML pipeline is:

```text
Sensor Data
     │
     ▼
Data Collection
     │
     ▼
Data Cleaning
     │
     ▼
Feature Engineering
     │
     ▼
Model Training
     │
     ▼
Model Evaluation
     │
     ▼
Prediction
```

## Software Stack

### Embedded

* **ESP32**
* C/C++ / ESP-IDF or Arduino framework
* I²C
* UART
* Wi-Fi

### Backend

* **Go**
* REST API
* Data processing
* Database integration

### Machine Learning

* **Python**
* NumPy
* Pandas
* Scikit-learn
* Matplotlib

### Frontend

* **React**
* JavaScript / TypeScript
* REST API

### Infrastructure

* Git
* Docker
* PostgreSQL

## Data Flow

```text
Sensors
   │
   ▼
ESP32
   │
   │ Wi-Fi
   ▼
Backend API
   │
   ├──────────────► Database
   │
   └──────────────► ML Pipeline
                         │
                         ▼
                    Predictions
                         │
                         ▼
                     Frontend
```

## Project Structure

```text
IOT-ML_Project/
│
├── firmware/             # ESP32 firmware
│   ├── sensors/          # Sensor drivers
│   ├── communication/    # Network communication
│   └── main/
│
├── backend/              # Go backend services
│   ├── cmd/
│   ├── internal/
│   ├── api/
│   └── migrations/
│
├── ml/                   # Machine learning
│   ├── datasets/
│   ├── preprocessing/
│   ├── models/
│   ├── training/
│   └── evaluation/
│
├── frontend/             # React web application
│
├── docs/                 # Project documentation
│
├── docker-compose.yml
└── README.md
```

## Main Objectives

The project focuses on the development of an integrated environmental monitoring platform rather than a standalone sensor device.

The key objectives are:

1. Design and develop an IoT environmental monitoring device.
2. Collect measurements from multiple environmental sensors.
3. Develop a reliable data transmission pipeline.
4. Store and process historical sensor data.
5. Develop machine learning models for environmental analysis.
6. Evaluate the accuracy of predictive models.
7. Provide a web interface for monitoring and analysis.
8. Investigate the possibility of forecasting environmental conditions.

## Current Development

The project is currently under active development.

Planned development stages:

* [ ] Design and manufacture the custom PCB
* [ ] Integrate ESP32 with environmental sensors
* [ ] Implement sensor data acquisition
* [ ] Implement communication with the backend
* [ ] Develop the data storage layer
* [ ] Collect a sufficiently large dataset
* [ ] Implement data preprocessing
* [ ] Train machine learning models
* [ ] Evaluate model performance
* [ ] Implement environmental forecasting
* [ ] Develop the monitoring dashboard
* [ ] Integrate the complete IoT → Backend → ML → Frontend pipeline

## Research Direction

The project explores the application of **Internet of Things and Machine Learning technologies for environmental monitoring**.

The collected data can be used to investigate how environmental parameters change over time and how combinations of measurements can be used to predict future conditions.

Particular attention is given to:

* temporal changes in CO₂ concentration;
* particulate matter concentration;
* temperature and humidity;
* atmospheric pressure;
* correlations between environmental parameters;
* detection of abnormal environmental conditions;
* short-term environmental forecasting.

## Goal

The final goal is to create a complete end-to-end environmental monitoring system:

```text
Physical Environment
        ↓
Environmental Sensors
        ↓
ESP32 IoT Device
        ↓
Data Transmission
        ↓
Go Backend
        ↓
Database
        ↓
Machine Learning
        ↓
Prediction & Analysis
        ↓
React Dashboard
```

This approach combines **embedded development, IoT, backend engineering, data science, and machine learning** into a single environmental monitoring platform.
