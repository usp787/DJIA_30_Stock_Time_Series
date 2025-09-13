# DJIA_30_Stock_Time_Series

A practice project implementing a Recurrent Neural Network (specifically an LSTM) to predict stock prices for Dow Jones Industrial Average (DJIA-30) companies.

---

## Table of Contents

- [Project Overview](#project-overview)  
- [Data](#data)  
- [Features & Preprocessing](#features--preprocessing)  
- [Model Architecture](#model-architecture)  
- [Usage](#usage)  
- [Evaluation](#evaluation)  
- [Results](#results)  
- [Requirements](#requirements)  
- [File Structure](#file-structure)  
- [Future Work](#future-work)  
- [License](#license)

---

## Project Overview

This project aims to predict stock closing prices (or possibly adjusted close) using an LSTM-based time‑series model. It explores historical DJIA‑30 stock data over time, leveraging feature scaling and deep learning to forecast future values.

---

## Data

- The dataset spans from **January 2005** through **end of 2017**.  
- Focus is on companies in the DJIA‑30 index.  
- Data includes historical stock prices; likely features such as open, high, low, volume, close.  

---

## Features & Preprocessing

- Data is scaled using scalers (e.g. for features and for target). Files included:  
  - `ibm_scaler_features.gz`  
  - `ibm_scaler_target.gz`  
- Selection of features and target likely involve closing prices (or “adj close”) depending on availability.  
- Time-series windows / sequences are built to feed into LSTM.  

---

## Model Architecture

- Uses a **Recurrent Neural Network (RNN)** architecture, more specifically **LSTM** (Long Short-Term Memory).  
- Trained on historical windows; predicts future stock values.  
- A trained model saved as `stock_predictor_lstm.pth`.  

---

## Usage

Here’s how to run / reproduce the project:

1. Clone the repository:  
   ```bash
   git clone https://github.com/usp787/DJIA_30_Stock_Time_Series.git
   cd DJIA_30_Stock_Time_Series
   ```

2. Set up your environment:  
   - Install Python (version ≥ 3.6 recommended)  
   - Install necessary libraries (see [Requirements](#requirements))  

3. Load the notebooks:  
   - `DJIA_30_Stock_Time_Series.ipynb` — main analysis and modeling notebook.  
   - `Google_closed_predict.ipynb` — possibly a specific example for Google stock.

4. If you want to make predictions:  
   - Load the trained model (`stock_predictor_lstm.pth`)  
   - Use the scalers to inverse transform predictions.  

---

## Evaluation

- Evaluate models using standard metrics for regression (e.g. RMSE, MAE).  
- Possibly use train/validation/test splits or cross-validation for time-series.  

---

## Results

- The model performance (details TBD depending on experiments).  
- Example prediction plots (real vs predicted).  

---

## Requirements

Here are likely required packages:

```text
python >= 3.6
numpy
pandas
matplotlib
scikit‑learn
torch
jupyter
```

---

## File Structure

Here’s how the files are organized:

```
DJIA_30_Stock_Time_Series/
│
├── DJIA_30_Stock_Time_Series.ipynb        # main modelling notebook
├── Google_closed_predict.ipynb            # example prediction for Google
├── stock_predictor_lstm.pth               # saved trained model
├── ibm_scaler_features.gz                 # scaler for features
├── ibm_scaler_target.gz                   # scaler for target variable
└── stock-time-series-20050101-to-20171231  # dataset folder or file
```

---

## Future Work

Some ideas to extend or improve:

- Use more recent data (beyond 2017) to improve model relevance.  
- Include more features (technical indicators, macroeconomic data, sentiment).  
- Experiment with different architectures: GRU, Transformer, or attention mechanisms.  
- Perform hyperparameter tuning (learning rate, number of layers, units).  
- Incorporate multivariate forecasting (predict multiple stocks jointly).  

---

## License

```
MIT License

Copyright (c) 2025 

Permission is hereby granted, free of charge, to any person obtaining a copy...
```
