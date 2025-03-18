# Weather Trend Forecasting

## Project Overview
This project focuses on forecasting weather trends using historical weather data. The dataset includes various meteorological parameters such as temperature, humidity, wind speed, air quality indices, and precipitation. The objective is to analyze weather trends and build predictive models to forecast temperature variations accurately.

## Dataset
The dataset used in this project was obtained from Kaggle: `Global Weather Repository`. It contains records of weather conditions across multiple locations, including parameters such as:
- Temperature (Celsius)
- Wind Speed and Direction
- Humidity Levels
- Air Quality Indices
- Precipitation Levels
- Moon Phase
- Visibility

## Methodology

### 1. Data Preprocessing
- Loaded the dataset and checked for missing values (none found).
- Performed outlier analysis and removed anomalies.
- Label-encoded categorical features such as `condition_text`, `wind_direction`, and `moon_phase`.
- Normalized numerical features using MinMaxScaler.

### 2. Exploratory Data Analysis (EDA)
- Visualized temperature distribution across different countries using box plots.
- Analyzed the correlation between temperature and other meteorological factors using a heatmap.
- Created histograms for precipitation and temperature distributions.
- Time-series analysis to observe seasonal weather patterns.

### 3. Forecasting Models

#### **SARIMA Model**
- Performed stationarity testing using the Augmented Dickey-Fuller (ADF) test.
- Differenced the time series to make it stationary.
- Used Auto-Correlation (ACF) and Partial Auto-Correlation (PACF) plots to determine the ARIMA parameters.
- Implemented the SARIMA model with seasonal trends to predict future temperatures.
- Evaluated the model using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

#### **Facebook Prophet Model**
- Reformatted the dataset for compatibility with Prophet (`ds` as datetime and `y` as temperature).
- Trained the Prophet model on historical data.
- Generated a future dataframe for forecasting.
- Visualized the forecasted temperature trends along with confidence intervals.
- Compared actual vs forecasted temperatures.
- Evaluated the model using MAE and RMSE.

## Results and Findings
- The SARIMA model successfully captured seasonality and produced reasonable forecasts, with a low MAE and RMSE.
- The Prophet model also performed well, providing interpretable insights into trend and seasonality.
- Key insights include:
  - Temperature variations closely correlate with precipitation and humidity.
  - There are identifiable seasonal trends in temperature changes.
  - The Prophet model's visualization of trends and seasonality provides an intuitive understanding of future weather patterns.

## Conclusion
This project demonstrates the effectiveness of time-series forecasting models in predicting weather trends. SARIMA and Prophet models both provide valuable insights, with SARIMA excelling in capturing fine-grained seasonality and Prophet offering a robust and visually interpretable forecast.

## Future Work
- Incorporate additional exogenous variables like atmospheric pressure, solar radiation, and altitude for improved forecasting accuracy.
- Experiment with deep learning models such as LSTMs for weather prediction.
- Deploy the model as a real-time weather forecasting web application.

## Installation and Usage
To run the project, follow these steps:

```bash
# Clone the repository
git clone https://github.com/Yarra-Hemanth/WeatherTrendForecasting.git
cd WeatherTrendForecasting

# Install required dependencies
pip install pandas numpy seaborn matplotlib scikit-learn statsmodels prophet

# Run the forecasting script
python weather_forecasting.py
```

## Acknowledgments
Special thanks to Kaggle for providing the dataset and open-source contributors for the development of forecasting libraries like Prophet and Statsmodels.

## Contact
For any queries, reach out via [LinkedIn](https://www.linkedin.com/in/hemanth-yarra-5a1775305) or email at hemanthyarra@gmail.com.
