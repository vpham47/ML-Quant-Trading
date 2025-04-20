# ML-Quant-Trading
**📈 Machine Learning Approaches in Quantitative Trading**
Authors: Hien Vinh Pham, Chery Lorika, Travis Lauren, Lumbantobing Johanna

Course: CX 4240 - Machine Learning Applications in Quantitative Trading

Semester: Spring 2025

**📄 Overview**
This project develops a machine learning-based strategy to generate daily BUY, HOLD, or SELL signals for selected stocks. We investigate the performance of three models:

- LSTM (Long Short-Term Memory)

- Random Forest Classifier

 Hybrid Model (LSTM + RF)

The main objective is to evaluate whether these models can outperform a traditional Buy-and-Hold strategy on private equity stocks using historical data from 2021 to 2024.

**📊 Data Sources and Features**
Stock Data: Daily price data from Yahoo Finance (yfinance)

Technical Indicators: RSI, MACD, Bollinger Bands

Macroeconomic Indicators: GDP, IPO Count, M&A Activities

Each model receives 13 engineered features derived from price history and macroeconomic metrics.

**🧪 Methodology**
Training: On Blackstone (BX) stock (Private Equity sector)

Testing: On APO, CG, KKR, ARES

Target Creation: 3-class classification using a non-overlapping look-ahead window to label BUY, HOLD, SELL

Backtesting: Simulated trading based on predicted signals compared to Buy-and-Hold strategy

Portfolio Optimization: Mean-Variance Optimization based on model returns

**🧠 Models and Hyperparameters**
LSTM
Units: 8

Dropout: 0.5

Optimizer: Adam (lr=1e-3)

Epochs: 50

Random Forest
n_estimators: 300

max_depth: 15

class_weight: 'balanced'

Hybrid
LSTM → softmax output → concatenated with features → RF classifier

Portfolio optimization further improves equity growth and reduces drawdowns

**🛠️ How to Run**
Clone this repo

Install dependencies (e.g., yfinance, scikit-learn, tensorflow, matplotlib)

!!!Remember also to download the macro.csv file!!!

**🔍 Key Takeaways**
LSTM captures sequential price trends but underperforms on generalizability

Random Forest performs well on macro + technical indicators

Hybrid model combines strengths of both for robust signal generation

Sector-specific training improves results — generalization across sectors is limited without additional feature engineering

Portfolio optimization adds tangible improvement to overall trading strategy performance

**📌 Future Work**
Incorporate dynamic thresholds

Add sector-specific macro indicators

Extend generalization to other industries (e.g., tech, banking)

Experiment with reinforcement learning for allocation strategies
