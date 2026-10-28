# DNN-Based Smart Energy Prediction and Optimization System

## 1. Project Overview

The DNN-Based Smart Energy Prediction and Optimization System is a software-only AI application that predicts future electricity consumption using historical energy data and a Deep Neural Network (DNN).

The system provides an interactive dashboard for energy forecasting, consumption analysis, anomaly detection, electricity bill estimation, and energy-saving recommendations.

**Domain:** Deep Learning, Artificial Intelligence, Energy Analytics

## 2. Objectives

- Predict future electricity consumption using a trained DNN model.
- Analyze historical energy consumption patterns.
- Forecast electricity usage for the next hour and next 24 hours.
- Detect unusual energy consumption.
- Estimate electricity bills in Indian rupees.
- Generate energy-saving recommendations.
- Display predictions and analytics through a web dashboard.

## 3. Technologies Used

| Component | Technology |
|---|---|
| Programming Language | Python 3.12 |
| Deep Learning | TensorFlow / Keras |
| Data Processing | Pandas, NumPy |
| Model Evaluation | Scikit-learn |
| Backend | FastAPI |
| Frontend | React, Vite |
| Charts | Recharts |
| Dataset | UCI Household Electric Power Consumption |
| API Communication | Fetch API |

## 4. System Architecture

1. Historical electricity consumption data is collected from a public dataset.
2. Data preprocessing removes or handles missing and invalid readings.
3. Time-based features are created for model training.
4. A DNN model is trained using historical consumption patterns.
5. The trained model predicts future energy consumption.
6. FastAPI provides predictions and analytics through REST endpoints.
7. The React dashboard displays energy usage, forecasts, estimated costs, and alerts.

## 5. Main Modules

### DNN Energy Prediction
Uses a trained neural network to estimate future electricity consumption.

### Energy Analytics
Displays historical consumption trends and forecast charts.

### Anomaly Detection
Identifies unusually high energy readings using a documented detection method.

### Electricity Bill Estimation
Calculates estimated electricity costs using consumption in kWh and a configurable rate per kWh.

### Recommendation System
Provides suggestions based on consumption patterns and detected anomalies.

### Web Dashboard
Offers a responsive interface for viewing forecasts, analytics, and system status.

## 6. Dataset

**Dataset:** Individual Household Electric Power Consumption

**Source:** UCI Machine Learning Repository

Dataset link:
https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption

The dataset contains household electricity measurements recorded at one-minute intervals over approximately four years.

The project should preprocess the data, handle missing values, create time-based features, and split training and testing data chronologically to prevent data leakage.

## 7. Project Folder Structure

```text
DNN-Smart-Energy-Prediction/
├── backend/
│   ├── main.py
│   ├── train_model.py
│   ├── preprocess_data.py
│   ├── requirements.txt
│   ├── data/
│   ├── models/
│   ├── services/
│   └── tests/
├── frontend/
│   ├── package.json
│   ├── index.html
│   └── src/
│       ├── App.jsx
│       ├── main.jsx
│       ├── components/
│       ├── pages/
│       ├── services/
│       └── styles/
├── README.md
└── .gitignore
```

The exact files and directories may vary slightly depending on the implementation.

## 8. Installation and Execution

### Prerequisites

- Python 3.12
- Node.js and npm
- Visual Studio Code
- Internet access for initial dependency installation and dataset download

### Step 1: Open the project

Open the project folder in VS Code.

Open the integrated PowerShell terminal and navigate to the project directory:

```powershell
cd "$HOME\OneDrive\Desktop\DNN-Smart-Energy-Prediction"
```

### Step 2: Create a Python virtual environment

```powershell
py -3.12 -m venv backend\.venv
```

### Step 3: Install backend dependencies

```powershell
.\backend\.venv\Scripts\python.exe -m pip install --upgrade pip
.\backend\.venv\Scripts\python.exe -m pip install -r backend\requirements.txt
```

### Step 4: Download and prepare the dataset

Follow the dataset download instructions provided in the project implementation. Place the downloaded data in the configured backend data directory.

Run the preprocessing script if required:

```powershell
.\backend\.venv\Scripts\python.exe backend\preprocess_data.py
```

### Step 5: Train the DNN model

```powershell
.\backend\.venv\Scripts\python.exe backend\train_model.py
```

Training should save the model and evaluation results to the configured output locations.

### Step 6: Start the backend

```powershell
.\backend\.venv\Scripts\python.exe -m uvicorn main:app --reload
```

Run this command from the `backend` directory, or use the equivalent command with the correct application module path.

Backend address:
http://127.0.0.1:8000

Interactive API documentation:
http://127.0.0.1:8000/docs

### Step 7: Start the frontend

Open a second VS Code terminal:

```powershell
cd "$HOME\OneDrive\Desktop\DNN-Smart-Energy-Prediction\frontend"
npm install
npm run dev
```

Open the local URL printed by Vite in the terminal, typically:

http://localhost:5173

## 9. Model Evaluation

Evaluate the model using a held-out chronological test dataset.

**Mean Absolute Error (MAE):** Measures the average absolute difference between actual and predicted consumption.

**Root Mean Squared Error (RMSE):** Measures prediction error while giving greater weight to larger errors.

Report the actual metrics produced by model evaluation. Do not enter assumed accuracy values or fabricated results.

## 10. Expected Outcomes

When correctly configured and executed, the application should:

- Train and save a DNN model.
- Generate forecasts from the trained model.
- Display energy consumption charts.
- Estimate electricity costs.
- Identify unusual readings.
- Provide consumption-based recommendations.
- Serve predictions through a FastAPI backend.
- Display backend data in the React dashboard.

## 11. Limitations

- Forecast quality depends on the dataset and model configuration.
- Household electricity patterns may not represent commercial or industrial usage.
- Predicted costs are estimates and may not include all electricity tariff rules.
- Anomaly alerts indicate unusual readings, not necessarily equipment faults.
- This software-only version does not measure live electricity consumption.

## 12. Future Enhancements

- Integrate IoT energy meters and ESP32 hardware.
- Add real-time electricity monitoring.
- Experiment with LSTM or other time-series forecasting models.
- Add user authentication and historical reports.
- Support multiple households or buildings.
- Improve recommendations using additional environmental and occupancy data.

## 13. Conclusion

The DNN-Based Smart Energy Prediction and Optimization System demonstrates how deep learning and web technologies can be combined to forecast electricity consumption, analyze energy usage, estimate costs, and identify unusual consumption patterns. The system can be extended with real-time monitoring and IoT integration in future versions.
