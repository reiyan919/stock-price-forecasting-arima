# 📈 Stock Price Forecasting Using Time Series Analysis (ARIMA)

## 📌 Project Overview

This project focuses on **time-series analysis and forecasting** of Apple Inc. (AAPL) stock prices using **statistical modeling techniques**.
The goal is to understand the temporal structure of financial data and generate **short-term forecasts** using the **ARIMA model**.

The project follows **standard academic methodology** used in economics, finance, and data science research.

---

## 📊 Dataset

* **Source**: Yahoo Finance
* **Stock**: Apple Inc. (AAPL)
* **Period**: 2010 – 2024
* **Frequency**: Daily
* **Features**:

  * Open
  * High
  * Low
  * Close
  * Volume

**Data access method**:

* Yahoo Finance website or `yfinance` Python library

**Source**
[https://finance.yahoo.com](https://finance.yahoo.com)
[https://pypi.org/project/yfinance/](https://pypi.org/project/yfinance/)

---

## 🧠 Methodology

The project follows a **structured time-series forecasting pipeline**:

---

### 🔹 Step 1 — Exploratory Time Series Analysis (EDA)

* Visualized the **closing price** over time
* Analyzed long-term trend and volatility
* Visualized **trading volume**
* Applied rolling mean to highlight trends

📌 **Insight**:
The series shows a strong upward trend and increasing variance, typical of financial time series.

**Reference**
[https://otexts.com/fpp3/exploratory.html](https://otexts.com/fpp3/exploratory.html)

---

### 🔹 Step 2 — Time-Series Decomposition (STL)

* Decomposed the closing price into:

  * Trend
  * Seasonality
  * Residuals
* Used **STL decomposition** with an annual trading period (252 days)

📌 **Insight**:
The trend component dominates, while seasonality is weak — a common characteristic of stock prices.

**Reference**
[https://www.statsmodels.org/stable/generated/statsmodels.tsa.seasonal.STL.html](https://www.statsmodels.org/stable/generated/statsmodels.tsa.seasonal.STL.html)

---

### 🔹 Step 3 — Stationarity Considerations

* Financial prices are **non-stationary**
* Stationarity is required for ARIMA models

📌 This motivates data transformation.

**Reference**
[https://www.investopedia.com/terms/s/stationary.asp](https://www.investopedia.com/terms/s/stationary.asp)

---

### 🔹 Step 4 — Data Transformation

To achieve stationarity:

* Applied **log transformation** to stabilize variance
* Applied **first differencing** to remove trend

📌 **Result**:
The transformed series exhibits more stable statistical properties.

**References**
[https://www.statsmodels.org/stable/tsa.html](https://www.statsmodels.org/stable/tsa.html)
[https://otexts.com/fpp3/arima.html](https://otexts.com/fpp3/arima.html)

---

### 🔹 Step 5 — ARIMA Parameter Identification (p, d, q)

* Used:

  * **ACF (Autocorrelation Function)** to identify `q`
  * **PACF (Partial Autocorrelation Function)** to identify `p`
* Differencing order set to `d = 1`

📌 **Rule**:

* `p` from PACF cutoff
* `q` from ACF cutoff

**References**
[https://www.statsmodels.org/stable/generated/statsmodels.graphics.tsaplots.plot_acf.html](https://www.statsmodels.org/stable/generated/statsmodels.graphics.tsaplots.plot_acf.html)
[https://www.statsmodels.org/stable/generated/statsmodels.graphics.tsaplots.plot_pacf.html](https://www.statsmodels.org/stable/generated/statsmodels.graphics.tsaplots.plot_pacf.html)

---

### 🔹 Step 6 — Model Training (ARIMA)

* Trained an **ARIMA model** on the transformed series
* Selected parameters based on ACF/PACF analysis
* Evaluated model diagnostics and information criteria (AIC)

📌 **Why ARIMA?**

* Statistically grounded
* Interpretable
* Widely used in academia and industry

**Reference**
[https://www.statsmodels.org/stable/generated/statsmodels.tsa.arima.model.ARIMA.html](https://www.statsmodels.org/stable/generated/statsmodels.tsa.arima.model.ARIMA.html)

---

### 🔹 Step 7 — Forecasting

* Generated **30-day forecasts**
* Visualized:

  * Historical prices
  * Forecasted values
  * Confidence intervals

📌 **Insight**:
Forecast uncertainty increases with the prediction horizon, which is expected in financial markets.

**Reference**
[https://www.statsmodels.org/stable/examples/notebooks/generated/tsa_arma_0.html](https://www.statsmodels.org/stable/examples/notebooks/generated/tsa_arma_0.html)

---

### 🔹 Step 8 — Model Evaluation

Evaluated forecasting accuracy using:

* **MAE (Mean Absolute Error)**
* **RMSE (Root Mean Squared Error)**
* **MAPE (Mean Absolute Percentage Error)**

📌 **Purpose**:
Ensure that forecasts are quantitatively reliable.

**References**
[https://otexts.com/fpp3/accuracy.html](https://otexts.com/fpp3/accuracy.html)
[https://scikit-learn.org/stable/modules/model_evaluation.html](https://scikit-learn.org/stable/modules/model_evaluation.html)

---

### 🔹 Step 9 — Residual Diagnostics

* Analyzed residuals to confirm:

  * Mean close to zero
  * No significant autocorrelation
  * Random (white noise–like) behavior

📌 **Conclusion**:
Residual diagnostics support the adequacy of the ARIMA model.

**Reference**
[https://www.statsmodels.org/stable/tsa.html](https://www.statsmodels.org/stable/tsa.html)

---

## 📌 Final Interpretation

* The Apple stock price series is **non-stationary** with strong long-term growth.
* Log transformation and differencing successfully stabilized the series.
* ARIMA modeling captured temporal dependencies effectively.
* Forecasts are suitable for **short-term analysis**, but long-term predictions remain uncertain due to market shocks and external factors.

---

## 🛠️ Tools & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Statsmodels
* Scikit-learn

---

## 🚀 Skills Demonstrated

* Time-series analysis
* Financial data handling
* Statistical modeling (ARIMA)
* Forecast evaluation
* Data visualization
* Analytical interpretation


