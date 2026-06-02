# Explainable IoT ML Microclimate Forecasting System

An explainable IoT and machine learning based microclimate forecasting system developed using FastAPI, React, ESP32, and machine learning models.

## Overview

It is a full-stack IoT-based weather monitoring and forecasting system. This project collects environmental sensor data using an ESP32-based hardware setup and sends the data to a FastAPI backend for storage, prediction, and explanation. This system predicts next-day rainfall, temperature, and humidity using trained machine learning models. It also uses Explainable AI to show why a prediction was made by displaying the contribution of important weather features. The frontend dashboard allows users to log in, view real-time sensor readings, observe recent weather trends, and inspect prediction explanations.

## Features

* Real-time weather data monitoring
* ESP32-based sensor data collection
* User registration and login system
* JWT-based authentication
* Sensor data storage using SQLite
* Rainfall prediction
* Temperature prediction
* Humidity prediction
* SHAP-based prediction explanation
* React-based user dashboard
* Recent weather trend visualization
* Station-based weather prediction

## Technologies Used

### Backend

* Python
* FastAPI
* SQLModel
* SQLite
* JWT Authentication
* bcrypt
* Scikit-learn
* XGBoost
* Joblib
* SHAP
* Pandas
* NumPy

### Frontend
* React
* JavaScript
* Axios
* Tailwind CSS
* Chart Visualization


## Hardware Components

* ESP32 Development Board
* DHT11 Temperature and Humidity Sensor
* Rain Sensor
* LDR Sensor
* MQ-6 Gas Sensor

## Machine Learning Models

This project uses trained machine learning models for weather forecasting tasks include:

* Rainfall classification model
* Temperature prediction model
* Humidity prediction model

The deployed models include:

* XGBoost Classifier
* XGBoost Regressor
* Random Forest-based Models

The backend loads the trained model files and uses current sensor values, lag features, rolling average features, seasonal features, and station information to generate predictions.

## Explainable AI

This system uses SHAP-based Explainable AI to make the machine learning predictions more understandable.

The explanation system shows the impact of different weather features such as:

* Temperature
* Humidity
* Rainfall
* Sunshine or LDR value
* Previous day weather values
* Rolling average weather values
* Seasonal information
* Station information

Each prediction includes feature contribution values and impact levels such as high, medium, and low.

## Project Structure

```text
ClimaCare-main/
│
├── Backend/
│   ├── xai.py                         # Main FastAPI backend with authentication, sensor data APIs, prediction, and explanation
│   ├── best_model.pkl                 # Trained rainfall prediction model
│   ├── temp_predictor.pkl             # Trained temperature prediction model
│   ├── humidity_predictor.pkl         # Trained humidity prediction model
│   ├── shap_meta.joblib               # SHAP metadata for model explanation
│   ├── shap_global_importance.json    # Global feature importance values
│   ├── database.db                    # SQLite database
│   └── requirements.txt               # Backend dependencies
│
├── Frontend/
│   ├── public/                        # Public frontend assets
│   ├── src/
│   │   ├── components/                # React components
│   │   ├── pages/                     # Application pages
│   │   ├── assets/                    # Images and logos
│   │   ├── App.jsx                    # Main React app routing
│   │   └── main.jsx                   # React entry point
│   ├── package.json                   # Frontend dependencies and scripts
│   └── vite.config.js                 # Vite configuration
│
├── BD_Weather.csv                     # Weather dataset used for model development
├── Sensor_Data.ino                    # ESP32 sensor data collection code
└── README.md                         # Project documentation
```

## Learning Purpose

Through this project, the following concepts were practiced:

* IoT sensor data collection
* ESP32-based environmental monitoring
* Backend API development using FastAPI
* User authentication using JWT
* SQLite database integration
* Machine learning model deployment
* Weather prediction using trained models
* Explainable AI using SHAP
* React frontend development
* Real-time dashboard visualization
* Full-stack IoT and ML system integration

## License

This project is open-source and available for learning, research, and educational purposes.
