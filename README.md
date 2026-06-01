# Explainable IoT ML Microclimate Forecasting System

An explainable IoT and machine learning based microclimate forecasting system developed using FastAPI, React, ESP32, and machine learning models.

## Overview

ClimaCare is a full-stack IoT-based weather monitoring and forecasting system. This project collects environmental sensor data using an ESP32-based hardware setup and sends the data to a FastAPI backend for storage, prediction, and explanation.

The system predicts next-day rainfall, temperature, and humidity using trained machine learning models. It also uses Explainable AI to show why a prediction was made by displaying the contribution of important weather features. The frontend dashboard allows users to log in, view real-time sensor readings, observe recent weather trends, and inspect prediction explanations.

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
* Feature impact visualization for weather forecasting
* React-based user dashboard
* Recent weather trend visualization
* Station-based weather prediction
* Beginner-friendly full-stack project structure
* Easy to customize and expand

## Technologies Used

* Python
* FastAPI
* SQLModel
* SQLite
* JWT Authentication
* bcrypt
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Joblib
* SHAP
* React
* Vite
* JavaScript
* Bootstrap
* React Bootstrap
* Chart.js
* Axios
* ESP32
* Arduino IDE

## Hardware Components

* ESP32 Development Board
* DHT11 Temperature and Humidity Sensor
* Rain Sensor
* LDR Sensor
* MQ-6 Gas Sensor

## Machine Learning Models

This project uses trained machine learning models for weather forecasting tasks.

The deployed models include:

* Rainfall classification model
* Temperature prediction model
* Humidity prediction model

The backend loads the trained model files and uses current sensor values, lag features, rolling average features, seasonal features, and station information to generate predictions.

## Explainable AI

ClimaCare uses SHAP-based Explainable AI to make the machine learning predictions more understandable.

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

## How to Run the Project

1. Clone the repository.
```bash
git clone <repository-link>
```
2. Open the project folder.
```bash
cd ClimaCare-main
```
3. Open the backend folder.
```bash
cd Backend
```
4. Create and activate a virtual environment.
```bash
python -m venv env
```
For Windows:
```bash
env\Scripts\activate
```
For Linux or macOS:
```bash
source env/bin/activate
```
5. Install the required backend dependencies.
```bash
pip install -r requirements.txt
```
6. Run the FastAPI backend server.
```bash
python -m fastapi dev xai.py
```
7. Open the backend API in your browser.
```text
http://127.0.0.1:8000
```
8. Open the FastAPI documentation.
```text
http://127.0.0.1:8000/docs
```
9. Open a new terminal and go to the frontend folder.
```bash
cd Frontend
```
10. Install the frontend dependencies.
```bash
npm install
```
11. Run the React frontend.
```bash
npm run dev
```
12. Open the frontend in your browser.
```text
http://localhost:5173
```

## API Endpoints

### Authentication

```text
POST /register
POST /token
```

### Sensor Data

```text
POST /send-data/
GET /data/user
GET /data/user/latest
```

### Prediction and Explanation

```text
POST /predict-explain
```

## Example Prediction Output

The prediction API returns:

* Rain tomorrow probability
* Rain tomorrow prediction
* Tomorrow temperature
* Tomorrow humidity
* SHAP-based feature contribution explanations
* Feature impact levels for rainfall, temperature, and humidity predictions

## Learning Purpose

This project was developed for learning, research, and practical implementation purposes. The main goal of this project is to understand how IoT sensor data, machine learning, backend APIs, frontend dashboards, and Explainable AI can be combined to build a real-time microclimate forecasting system.

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

## Research Purpose

ClimaCare aims to provide a low-cost, explainable, and real-time weather forecasting solution for microclimate monitoring. The system can support applications in agriculture, environmental monitoring, smart farming, and local weather-based decision support.

## License

This project is open-source and available for learning, research, and educational purposes.
## License

This project is licensed under the MIT License.
