# Automatic Tire Inflation System (ATIS) using AUTOSAR and Machine Learning

## 📘 Overview

This project presents an **AUTOSAR-compliant Automatic Tire Inflation System (ATIS)** for heavy-duty vehicles, featuring dynamic pressure adjustment across multiple driving modes (Highway, Off-road, and Traffic). It ensures real-time tire pressure regulation using an onboard compressor, **Tire Pressure Monitoring System (TPMS)**, and intelligent **puncture detection via a Machine Learning model**.

The system is designed to improve:
- Vehicle **safety**
- **Fuel efficiency**
- **Tire longevity**

---

## 🎯 Key Features

- **Dynamic Tire Pressure Modes**: Automatically adjusts tire pressure based on driving conditions.
- **Onboard TPMS Integration**: Real-time tire pressure and temperature sensing.
- **Machine Learning-Based Puncture Detection**: Early detection of air leaks or rapid punctures.
- **AUTOSAR-Based Architecture**: Seamless integration with ECUs, DEM, FIM, NvM, and BSW modules.
- **MATLAB Simulink Integration**: For model-based design and ARXML file generation.
- **Fault Management**: Logs puncture events, manages compressor behavior, and triggers alerts.

---

## 🧠 Machine Learning Model – Puncture Detection

A **supervised ML model** is integrated into the ATIS application layer to classify tire punctures and control air loss through predictive analysis. The model is trained on pressure profile data mimicking real-world deflation scenarios.

### 🔍 ML Workflow

1. **Data Preprocessing**
   - Imputation of missing values
   - StandardScaler normalization
   - Principal Component Analysis (PCA) to reduce dimensionality

2. **Class Imbalance Handling**
   - **SMOTE (Synthetic Minority Over-sampling Technique)** used to balance classes

3. **Model Training**
   - **K-Nearest Neighbors (KNN)** and **Support Vector Machine (SVM)** were tuned using GridSearchCV
   - Selection based on **ROC-AUC** score

4. **Deployment**
   - Integrated in the **TPMS ECU** to detect pressure anomalies and activate inflation/deflation actions via the ATIS ECU

---

## 🛠 AUTOSAR Integration

Key AUTOSAR modules and layers used:

- **Application Layer**: Hosts ML logic and inflation control
- **RTE (Runtime Environment)**: Facilitates SWC communication
- **BSW Modules**: Include TPMS driver, compressor control, and diagnostics
- **NvM**: Stores pressure history and calibration data
- **DEM & FIM**: Handles diagnostics and fault constraints

---

## 🧪 Validation and Testing

- **Simulated puncture events** for testing detection speed and accuracy
- **Driving mode testing** under highway, off-road, and traffic simulations
- **Environmental stress testing** to assess performance under variable temperature and load

Performance metrics included:
- **Response time to puncture**
- **Inflation/deflation efficiency**
- **ECU communication compliance**

---

## 📂 Project Structure

```
├── ML_Model/
│   ├── preprocessing.py          # Data cleaning and PCA
│   ├── model_training.py         # Training and saving ML model
│   ├── tuner.py                  # Hyperparameter tuning with GridSearchCV
├── AUTOSAR/
│   ├── Simulink_Model.slx        # MATLAB Simulink model
│   └── ARXML_Files/              # Generated for ECU deployment
├── Documentation/
│   ├── ATIS_Report_Final.pdf     # Full report with architecture and evaluation
├── README.md                     # This file
```

---

## 📌 Conclusion

The developed ATIS system:
- Dynamically adapts to road conditions
- Detects punctures early using ML
- Follows AUTOSAR standards for automotive deployment

This system represents a scalable, intelligent tire pressure control solution for enhancing modern vehicle safety and performance.


