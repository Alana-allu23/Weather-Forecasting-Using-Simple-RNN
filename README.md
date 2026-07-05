# Weather-Forecasting-Using-Simple-RNN
Project Overview

This project implements a Simple Recurrent Neural Network (SimpleRNN) to forecast daily temperatures using historical weather data. The model is trained on daily weather features such as Temperature, Humidity, and Wind Speed to predict the next day's temperature. After training, the model is used to forecast the next seven days of temperature.

Objective

The objective of this project is to:

Preprocess historical weather data.
Build a SimpleRNN model for time-series forecasting.
Predict daily temperature using the previous 7 days of weather data.
Evaluate the model using RMSE, MAE, and R² Score.
Forecast temperatures for the next seven days.

Dataset

The dataset contains historical weather observations with attributes including:

Formatted Date
Temperature (°C)
Humidity
Wind Speed (km/h)
Pressure (millibars)

The data is converted into daily averages before training the model.

Technologies Used
Python 3
NumPy
Pandas
Matplotlib
Scikit-learn
TensorFlow / Keras

Project Workflow

1. Data Preprocessing
Load the dataset.
Convert the Formatted Date column into datetime format.
Extract only the date.
Group data by date and calculate daily averages.
Handle missing values using forward fill.

2. Feature Selection

The following features are used as model inputs:

Temperature (°C)
Humidity
Wind Speed (km/h)

3. Data Normalization

The selected features are normalized using MinMaxScaler to scale values between 0 and 1.

4. Sequence Creation

A sliding window approach is used.

Input: Previous 7 days of weather data.
Output: Temperature of the next day.

5. Dataset Split

The prepared sequences are divided into:

70% Training Data
15% Validation Data
15% Testing Data

The data is split sequentially because this is a time-series forecasting problem.

6. Model Architecture

The SimpleRNN model consists of:

SimpleRNN Layer (64 units)
Dropout Layer (0.2)
Dense Output Layer (1 neuron)

7. Model Training

The model is trained for 50 epochs using the training dataset while monitoring validation loss.

8. Model Evaluation

Performance is evaluated using:

Root Mean Squared Error (RMSE)
Mean Absolute Error (MAE)
R² Score

Example Results:

RMSE: 2.01°C
MAE: 1.56°C
R² Score: 0.94

These results indicate good prediction accuracy.

9. Future Forecast

The trained model predicts the temperature for the next 7 days using the most recent weather observations.

Example Forecast:

Day	Predicted Temperature (°C)
Day 1	1.20
Day 2	2.31
Day 3	3.17
Day 4	3.86
Day 5	4.42
Day 6	4.93
Day 7	5.40
Output Graphs

The project generates the following visualizations:

Daily Temperature Trend
Training vs Validation Loss
Actual vs Predicted Temperature
7-Day Temperature Forecast

Output Graphs

The project generates the following visualizations:

Daily Temperature Trend
Training vs Validation Loss
Actual vs Predicted Temperature
7-Day Temperature Forecast

Project Structure
Weather_Forecasting/
│
├── weatherHistory.csv
├── weather_forecasting.ipynb
├── README.md
└── requirements.txt

Results

The SimpleRNN model successfully learned historical weather patterns and produced accurate daily temperature predictions. The evaluation metrics indicate strong model performance, and the generated 7-day forecast demonstrates the model's ability to predict future temperature trends.

Conclusion

This project demonstrates the use of a Simple Recurrent Neural Network (SimpleRNN) for time-series weather forecasting. By using the previous seven days of weather information, the model predicts future daily temperatures with good accuracy. The project highlights the effectiveness of recurrent neural networks for sequential data and provides a practical approach to short-term weather prediction.
