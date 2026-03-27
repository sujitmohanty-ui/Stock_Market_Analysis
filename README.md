# 📈 Stock Market Trend Analysis & Prediction

## 📌 Project Overview

This project focuses on analyzing and predicting stock market trends using **data analytics, visualization, and machine learning techniques**. It combines **technical analysis** with **LSTM-based deep learning models** to understand stock behavior and forecast future prices.

The project is implemented using **Python, Jupyter Notebook, and financial APIs** and uses real-world stock data.

---

## 🎯 Objectives

* Analyze historical stock market data
* Identify trends using **moving averages & statistical techniques**
* Visualize stock performance
* Predict future prices using **LSTM (Deep Learning)**
* Compare multiple stocks (AAPL, GOOG, MSFT, AMZN)

---

## 🗂️ Project Structure

```
📦 Stock-Market-Analysis
 ┣ 📜 Stock_Market_Analysis.ipynb   # Main notebook
 ┣ 📜 Stock_Market_Data.csv        # Dataset
 ┣ 📜 Stock_Market_Report.pdf      # Project report
 ┣ 📜 README.md                   # Documentation
```

---

## ⚙️ Technologies Used

* **Programming Language:** Python

* **Libraries:**

  * pandas, numpy
  * matplotlib, seaborn, plotly
  * yfinance
  * sklearn
  * keras (LSTM Model)

* **Tools:**

  * Jupyter Notebook
  * Google Colab
  * VS Code
  * GitHub

---

## 📊 Dataset

* Source: Kaggle + Yahoo Finance API
* Contains:

  * Stock prices (Open, Close, Adj Close)
  * Volume
  * Time-series data

---

## 🔄 Workflow

### 1. Data Collection

* Stock data fetched using `yfinance`
* CSV dataset used for initial analysis

### 2. Data Preprocessing

* Handling missing values
* Data normalization using `MinMaxScaler`

### 3. Data Analysis & Visualization

* Closing price trends
* Volume analysis
* Moving averages
* Correlation heatmaps

### 4. Prediction Model

* LSTM (Long Short-Term Memory) neural network
* Time-series forecasting

---

## 💻 Key Code Snippets

### 📌 1. Fetching Stock Data

```python
import yfinance as yf
from datetime import datetime

tech_list = ['AAPL', 'GOOG', 'MSFT', 'AMZN']
start = datetime(2024, 1, 1)
end = datetime.now()

data = yf.download(tech_list, start=start, end=end)
```

---

### 📌 2. Moving Average Calculation

```python
ma_day = [10, 20, 50]

for company in company_list:
    for ma in ma_day:
        company[f"MA for {ma} days"] = company['Close'].rolling(ma).mean()
```

---

### 📌 3. Daily Returns

```python
company['Daily Return'] = company['Close'].pct_change()
```

---

### 📌 4. LSTM Model

```python
from keras.models import Sequential
from keras.layers import Dense, LSTM

model = Sequential()
model.add(LSTM(128, return_sequences=True, input_shape=(60,1)))
model.add(LSTM(64))
model.add(Dense(25))
model.add(Dense(1))

model.compile(optimizer='adam', loss='mean_squared_error')
model.fit(x_train, y_train, batch_size=1, epochs=1)
```

---

### 📌 5. Model Evaluation (RMSE)

```python
import numpy as np

rmse = np.sqrt(np.mean((predictions - y_test) ** 2))
print("RMSE:", rmse)
```

---

## 📈 Features

* 📊 Stock price visualization
* 📉 Trend analysis using moving averages
* 🔗 Correlation between stocks
* 📦 Multi-stock comparison
* 🤖 LSTM-based prediction model
* 📊 Interactive plots using Seaborn & Matplotlib

---

## 📊 Results

* Successfully visualized stock trends and patterns
* Identified relationships between major tech stocks
* Built a working **LSTM model for prediction**
* Achieved reasonable accuracy (low RMSE)

---

## 🚀 How to Run

1. Clone the repository

```bash
git clone https://github.com/your-username/stock-market-analysis.git
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Run the notebook

```bash
jupyter notebook Stock_Market_Analysis.ipynb
```

---

## 👥 Contributors (Blame Section)

| Name                   | Role                            |
| ---------------------- | ------------------------------- |
| Sujit Mohanty          | Data Analysis, LSTM Model       |
| Pratyush Kumar Pradhan | Data Collection & Preprocessing |
| B S Arman              | Visualization & Testing         |
| Ankit Kumar Dey        | Backend & Integration           |

> GitHub automatically tracks contributions using `git blame` and commit history.

---

## 📌 Future Enhancements

* Add **real-time prediction dashboard (Streamlit)**
* Improve model accuracy with **GRU / Transformer models**
* Deploy as a web application
* Add more stocks & financial indicators

---

## 📜 Conclusion

This project demonstrates how **data science and machine learning** can be applied to financial markets. It transforms raw stock data into meaningful insights and predictions, helping users make informed investment decisions.

---

## 📚 References

* Yahoo Finance API (`yfinance`)
* Kaggle datasets
* Scikit-learn documentation
* Keras & TensorFlow documentation

---

## ⭐ If you like this project

Give it a ⭐ on GitHub and share it!

---

If you want, I can also:

* Generate a **`requirements.txt`**
* Create a **GitHub repo description + tags**
* Or fix your notebook errors before upload 👍
