# Traffic Flow Prediction using LSTM

## Overview

This project focuses on predicting future traffic speed using a Long Short-Term Memory (LSTM) neural network. I used the **METR-LA** dataset, a subset of the Caltrans PeMS traffic dataset, which contains traffic speed data collected from multiple sensors at 5-minute intervals.

The goal was to train an LSTM model to learn patterns from historical traffic data and predict the next traffic speed value based on the previous observations.

## What I Did

* Loaded and explored the traffic dataset.
* Cleaned the data by handling invalid and missing values.
* Normalized the traffic speed values using MinMaxScaler.
* Created time sequences for training the LSTM model.
* Trained and evaluated the model using MAE and RMSE.
* Visualized the results by comparing actual and predicted traffic speeds.
* Saved the trained model and scaler for future use.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* TensorFlow / Keras

## Results

The trained LSTM model was able to capture traffic patterns and produce accurate traffic speed predictions with a low prediction error. This project helped me understand the complete workflow of a time-series forecasting problem, from data preprocessing and sequence generation to model training, evaluation, and visualization.
