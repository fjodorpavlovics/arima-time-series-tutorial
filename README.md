# ARIMA Time-Series Modelling and Forecasting

A fully annotated Python tutorial demonstrating the statistical foundations, estimation and evaluation of ARIMA models through a monthly hot dog sales example.

## Project Overview

The purpose of this project is to explain the complete ARIMA modelling process in both mathematical and natural language. The dataset is intentionally simple so that the main focus remains on understanding the statistical concepts, model-building decisions and interpretation of the results.

## Topics Covered

* time-series data preparation and visualisation;
* rolling mean and rolling standard deviation;
* weak stationarity;
* Augmented Dickey–Fuller and KPSS tests;
* first-order differencing;
* autoregressive and moving-average processes;
* ARIMA parameters;
* ACF and PACF analysis;
* maximum likelihood estimation;
* point forecasts and forecast intervals;
* residual diagnostics;
* chronological train–test evaluation;
* automated ARIMA selection using AIC;
* ME, MAE, MSE, RMSE and MAPE.

## Dataset

The dataset contains monthly hot dog sales observations from January 2021 to October 2024.

* `trx_month`: month of observation;
* `hot_dog_sales_pcs`: number of hot dogs sold during the month.

The dataset is located in:

```text
data/hot_dog_sales.csv
```

## Repository Structure

```text
arima-time-series-tutorial
│
├── data
│   ├── README.md
│   └── hot_dog_sales.csv
│
├── arima_time_series_tutorial.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Main Results

The original sales series was found to be non-stationary. The ADF test did not reject the unit-root hypothesis, while the KPSS test rejected level stationarity.

After first-order differencing, both tests supported treating the transformed series as stationary. The ACF and PACF plots did not indicate clear low-order AR or MA structures, leading to ARIMA$(0,1,0)$ as the baseline specification.

The automated ARIMA procedure selected the same model using AIC. However, holdout evaluation showed that the model systematically underestimated sales during the later test period. This demonstrates why good in-sample model selection does not automatically guarantee accurate future forecasts.

## Requirements

The project uses:

* Python
* Jupyter Notebook
* NumPy
* pandas
* Matplotlib
* Seaborn
* scikit-learn
* statsmodels
* pmdarima

Install the required packages with:

```bash
pip install -r requirements.txt
```

## Running the Project

1. Clone or download this repository.
2. Install the packages listed in `requirements.txt`.
3. Open `arima_time_series_tutorial.ipynb`.
4. Run the notebook cells sequentially from top to bottom.

The notebook loads the dataset using the following relative path:

```python
file_path = 'data/hot_dog_sales.csv'
```

## Purpose and Scope

This project is an educational case study rather than a production forecasting system. Its main objective is to demonstrate the mathematical foundations, practical implementation and critical evaluation of ARIMA time-series models.
