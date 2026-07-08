# Traffic Flow Prediction using LSTM

## Project Overview

This project implements a Long Short-Term Memory (LSTM) neural network to predict future traffic conditions using historical traffic sensor data.

The assignment recommends using the Caltrans PeMS dataset. For this implementation, the **METR-LA** subset of the Caltrans PeMS dataset was used.

Although the assignment mentions **traffic density prediction**, the METR-LA dataset actually contains **traffic speed measurements** collected from road sensors. Therefore, this project predicts the **next traffic speed value** of a selected sensor using its previous traffic speed readings.
---

## Objective

The objective of this project is to build a deep learning model capable of learning traffic patterns over time and predicting the next traffic speed value using historical observations.

---

## Dataset

Dataset Used:
- METR-LA (Derived from Caltrans PeMS)

Dataset Characteristics:
- 34,272 time-stamped observations
- 207 traffic sensors
- Measurements recorded every 5 minutes
- Each column represents one traffic sensor
- Each value represents the average traffic speed recorded by that sensor

For simplicity, one sensor was selected and treated as a univariate time-series forecasting problem.

---

## Project Workflow

1. Load the traffic dataset.
2. Perform Exploratory Data Analysis (EDA).
3. Detect invalid zero readings.
4. Replace invalid zero values with NaN.
5. Fill missing values using linear interpolation.
6. Normalize the traffic speed values using MinMaxScaler.
7. Create time sequences of the previous 10 observations.
8. Split the data into training and testing sets.
9. Build an LSTM model using Keras.
10. Train the model.
11. Predict traffic speed on the test dataset.
12. Evaluate the model using MAE and RMSE.
13. Save the trained model and scaler.

---

## Data Preprocessing

The dataset contained several timestamps where every sensor recorded a value of zero.

Since these zero values occurred simultaneously across all sensors, they were treated as invalid sensor readings rather than actual traffic conditions.

The preprocessing steps included:

- Replace zero values with NaN
- Apply linear interpolation
- Forward fill remaining missing values
- Backward fill remaining missing values
- Normalize data using MinMaxScaler

---

## Model Architecture

Framework:
- TensorFlow
- Keras

Model:

- LSTM Layer (50 Units)
- Dense Output Layer (1 Unit)

Loss Function:
- Mean Squared Error (MSE)

Optimizer:
- Adam

Epochs:
- 10

Batch Size:
- 32

---

## Input and Output

Input:

Previous 10 traffic speed readings from one traffic sensor.

Output:

The predicted traffic speed for the next time step.

Example:

Input:
```
62
61
60
63
65
64
62
61
60
59
```

Prediction:

```
61
```

---

## Evaluation Metrics

The trained model was evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

Obtained Results:

- MAE ≈ 3
- RMSE ≈ 4

These values indicate that the model predicts traffic speed with relatively small average error.

---

## Visualizations

The notebook includes:

- Dataset Distribution Histogram
- Traffic Speed over Time
- Traffic Speed after Data Cleaning
- Correlation Heatmap
- Training Loss Curve
- Actual vs Predicted Traffic Speed

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow
- Keras

---

## Conclusion

This project demonstrates how an LSTM neural network can learn temporal patterns from historical traffic speed data and predict future traffic speed values.

The model successfully captures traffic trends using previous observations and achieves good prediction accuracy on the testing dataset. The project also highlights the importance of preprocessing time-series data before training deep learning models.