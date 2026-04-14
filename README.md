# Multi-Crypto Price Direction Prediction using Machine Learning

##  Project Overview
This project focuses on predicting the **short-term price direction (up or down)** of multiple cryptocurrencies using machine learning techniques.

Using historical market data from Bybit at **15-minute intervals**, the problem is formulated as a **binary classification task**, where the model predicts whether the next price movement will be upward or downward.


##  Objectives
The main objectives of this project are:
- To analyze cryptocurrency market behavior using historical data  
- To build and compare multiple machine learning models  
- To apply proper time-series validation techniques  
- To understand the challenges of financial prediction  

 
## Dataset Description
The dataset consists of historical price data for the following cryptocurrencies:
- BTCUSDT  
- ETHUSDT  
- DOGEUSDT  
- SOLUSDT  
- XRPUSDT  

**Key characteristics:**
- Timeframe: 15-minute intervals  
- Features include: Open, High, Low, Close, Volume  
- Data combined into a single dataset for multi-asset learning  


##  Methodology

### 1. Data Preprocessing
- Merged multiple CSV files into a unified dataset  
- Converted timestamps into datetime format  
- Checked and handled missing values and duplicates  


### 2. Target Variable Construction
A binary target variable was created:
- `1` → Price increases in the next time step  
- `0` → Price decreases in the next time step  

Care was taken to **avoid data leakage** by ensuring that future information was not used in training.


### 3. Feature Engineering
To improve model performance, several features were engineered:
- **Returns** (percentage price changes)  
- **Lag features** (previous time steps)  
- **Rolling statistics**:
  - Moving averages (trend)
  - Standard deviation (volatility)  


### 4. Train-Test Split
Since this is time-series data:
- A **time-based split** was used instead of random sampling  
- The **last 365 days** of data were reserved for testing  
- This ensures realistic evaluation and avoids look-ahead bias  


##  Models Implemented
The following machine learning models were trained and evaluated:

- **Linear Regression** (baseline approach)  
- **Logistic Regression**  
- **Random Forest Classifier**  
- **XGBoost Classifier**  


##  Evaluation Metrics
Model performance was evaluated using:
- Accuracy  
- F1 Score  
- ROC-AUC Score  
- Balanced Accuracy  


##  Results & Discussion
- Tree-based models such as **Random Forest** and **XGBoost** performed better than linear models  
- Feature engineering significantly improved predictive performance  
- Despite improvements, predicting financial markets remains challenging due to high volatility and noise  


##  Tools and Technologies
- Python  
- Pandas & NumPy  
- Scikit-learn  
- XGBoost  
- Matplotlib  

##  How to Run the Project

```bash
git clone https://github.com/your-username/ml_final_project.git
cd ml_final_project
pip install pandas numpy scikit-learn matplotlib xgboost
jupyter notebook
