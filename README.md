
# Time Series Load Forecasting using SARIMAX

This project demonstrates how to forecast electrical load data using the **SARIMAX** model from `statsmodels`. It includes hourly-resolution time series data preprocessing, training, multi-step forecasting, evaluation, and visualization.

---

## Dataset

The dataset used is from the **Open Power System Data (OPSD)** platform and includes hourly load data for Austria.

- **Source**: [Open Power System Data](https://data.open-power-system-data.org/)
- **Columns used**:
  - `utc_timestamp`: Timestamp of each data point
  - `AT_load_actual_entsoe_transparency`: Actual load in Austria

---

## Methods Used

### Preprocessing
- Converted timestamps to proper datetime format
- Removed time zone suffixes (`Z`, `T`)
- Resampled and cleaned the data
- Scaled the data using `MinMaxScaler` (normalized for modeling)

### Modeling
- Applied SARIMAX model:  
  **Order** = (4, 1, 0)  
  **Seasonal Order** = (1, 1, 0, 24)
- Used a **rolling forecast** approach for multi-step predictions

### Evaluation
- Inverse transformed predictions for interpretation
- Used **Mean Absolute Error (MAE)** per forecast horizon
- Plotted actual vs predicted values for clear visual comparison

---

## Forecast Horizons

This project supports **multi-step forecasting** (e.g., next 3 hours). Each step in the future is evaluated and visualized separately with decaying line thickness to show uncertainty.


## Dependencies

Install the required Python packages:

```bash
pip install pandas numpy matplotlib scikit-learn statsmodels
```

---

## How to Run

1. Download the dataset and place it in a `data/` folder
2. Open the notebook:
   ```bash
   jupyter notebook sarimax_forecasting.ipynb
   ```
3. Run all cells to preprocess, train, and visualize predictions

---

## Key Learnings

- How to preprocess hourly time series data
- How SARIMAX handles seasonality and autoregression
- How to forecast multiple time steps using a rolling window
- How to visualize and evaluate model performance


