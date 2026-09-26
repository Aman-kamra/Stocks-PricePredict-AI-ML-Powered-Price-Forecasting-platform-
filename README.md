# 📈 Stock PricePrediction : AIML   powered price forecasting platform

An AI-powered stock price prediction platform that leverages multiple machine learning models to provide comprehensive market analysis and predictions.

![Python](https://img.shields.io/badge/Python-3.10-green)
![React](https://img.shields.io/badge/React-18.2-blue)

## 🌟 Features

### Multi-Model Predictions
- **Linear Regression** - Simple trend analysis with bar charts
- **Random Forest** - Ensemble learning with line charts  
- **XGBoost** - Gradient boosting with area charts
- **LSTM (Deep Learning)** - Neural network-based predictions with candlestick-style charts

### Real-Time Data
- Live stock data fetching from Yahoo Finance
- Support for global markets (US, India, UK, Japan, Europe, etc.)
- Automatic currency detection and display (USD $, INR ₹, GBP £, EUR €, JPY ¥)

### Sentiment Analysis
- News scraping for stock-related articles
- Sentiment analysis using NLP
- Integration of sentiment data with price predictions

### Interactive Dashboard
- Clean, card-based UI with 2x2 grid layout
- Multiple chart types for different models
- Real-time prediction updates
- Responsive design

## 🏗️ Architecture

```
StockSense AI/
├── app/
│   ├── backend/          # Flask REST API
│   │   ├── routes/       # API endpoints
│   │   └── utils/        # Model runners
│   └── frontend/         # React + Vite
│       └── src/
│           ├── components/
│           ├── pages/
│           └── api/
├── data/                 # Data processing
├── models/              # ML model training
├── sentiment/           # News & sentiment analysis
├── portfolio/           # Portfolio simulation
└── risk/               # Risk analysis tools
```

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- Node.js 16+
- npm or yarn

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/Kush05Bhardwaj/Stocksense-AI.git
cd "StockSense AI"
```

2. **Set up Python environment**
```bash
python -m venv venv
.\venv\Scripts\activate  # On Windows
source venv/bin/activate # On Mac/Linux

pip install -r requirements.txt
```

3. **Set up Frontend**
```bash
cd app/frontend
npm install
```

### Running the Application

1. **Start the Backend Server**
```bash
# From project root
.\venv\Scripts\activate
python app/backend/app.py
```
Backend runs on: `http://localhost:5000`

2. **Start the Frontend**
```bash
cd app/frontend
npm start
```
Frontend runs on: `http://localhost:3000`

3. **Access the Application**
Open your browser and navigate to: `http://localhost:3000`

## 📊 Usage

### Making Predictions

1. Enter a stock symbol in the search box:
   - **US Stocks**: `AAPL`, `MSFT`, `GOOGL`, `TSLA`
   - **Indian Stocks**: `RELIANCE.NS`, `TCS.NS`, `INFY.NS`
   - **Japanese Stocks**: `7203.T` (Toyota), `9984.T` (SoftBank)
   - **UK Stocks**: `BP.L`, `HSBA.L`

2. Click "Predict" to get predictions from all 4 models

3. View results in the card layout:
   - Current price
   - Predicted prices from each model
   - Expected change percentage
   - Visual charts for each prediction

### Data Collection (Optional)

For training custom models:

```bash
# 1. Fetch stock data
python data/fetch_data.py

# 2. Scrape news
python sentiment/news_scraper.py

# 3. Analyze sentiment
python sentiment/sentiment_analyzer.py

# 4. Merge data
python sentiment/merge_sentiment.py

# 5. Compare models
python models/compare_models.py

# 6. Train LSTM
python models/lstm_model.py
```

## 🛠️ Technology Stack

### Backend
- **Flask** - Web framework
- **yFinance** - Stock data API
- **pandas** - Data manipulation
- **scikit-learn** - ML models (Linear Regression, Random Forest)
- **XGBoost** - Gradient boosting
- **TensorFlow/Keras** - Deep learning (LSTM)
- **TextBlob** - Sentiment analysis
- **NewsAPI** - News data

### Frontend
- **React 18** - UI framework
- **Vite** - Build tool and dev server
- **Axios** - HTTP client
- **Recharts** - Data visualization
- **CSS3** - Styling

### Data & ML
- **NumPy** - Numerical computing
- **Matplotlib/Seaborn** - Data visualization
- **BeautifulSoup4** - Web scraping

## 📁 Project Structure

```
StockSense AI/
│
├── app/
│   ├── backend/
│   │   ├── app.py                    # Flask application entry point
│   │   ├── routes/
│   │   │   ├── predict.py           # Prediction endpoints
│   │   │   ├── portfolio.py         # Portfolio management
│   │   │   └── sentiment.py         # Sentiment analysis
│   │   └── utils/
│   │       ├── model_runner.py      # ML model execution
│   │       └── risk_runner.py       # Risk calculations
│   │
│   └── frontend/
│       ├── src/
│       │   ├── components/
│       │   │   ├── StockSearch.jsx  # Main search component
│       │   │   └── PredictionCard.jsx
│       │   ├── pages/
│       │   │   ├── Dashboard.jsx    # Main dashboard
│       │   │   └── Portfolio.jsx    # Portfolio view
│       │   ├── api/
│       │   │   └── api.js           # API integration
│       │   ├── App.jsx              # Root component
│       │   └── main.jsx             # Entry point
│       ├── index.html
│       ├── vite.config.js
│       └── package.json
│
├── data/
│   ├── fetch_data.py               # Stock data fetching
│   ├── visualize.py                # Data visualization
│   ├── raw/                        # Raw data storage
│   ├── processed/                  # Processed data
│   └── visualizations/             # Charts and graphs
│
├── models/
│   ├── prepare_data.py             # Feature engineering
│   ├── linear_model.py             # Linear Regression
│   ├── rf_model.py                 # Random Forest
│   ├── xgb_model.py                # XGBoost
│   ├── lstm_model.py               # LSTM Neural Network
│   └── compare_models.py           # Model comparison
│
├── sentiment/
│   ├── news_scraper.py             # News article scraping
│   ├── sentiment_analyzer.py       # Sentiment analysis
│   └── merge_sentiment.py          # Data integration
│
├── portfolio/
│   └── simulator.py                # Portfolio simulation
│
├── risk/
│   ├── volatility.py               # Volatility calculations
│   └── confidence.py               # Confidence intervals
│
├── requirements.txt                # Python dependencies
├── .gitignore                      # Git ignore rules
└── README.md                       # This file
```

## 🎯 API Endpoints

### Prediction
```http
POST /api/predict
Content-Type: application/json

{
  "symbol": "AAPL"
}

Response:
{
  "symbol": "AAPL",
  "company_name": "Apple Inc.",
  "current_price": 230.45,
  "currency": "$",
  "predictions": [
    {
      "model": "Linear Regression",
      "prediction": 232.10,
      "change": 0.72
    },
    ...
  ]
}
```

## 🔧 Configuration

### Backend Configuration
Edit `app/backend/app.py`:
- Port: Default `5000`
- Debug mode: `True` for development

### Frontend Configuration
Edit `app/frontend/vite.config.js`:
- Port: Default `3000`
- Proxy: Routes `/api/*` to backend

## 📈 Model Performance

Based on AAPL stock data (2020-2026):

| Model | MAE | RMSE | Type |
|-------|-----|------|------|
| Linear Regression | 2.5 | 3.1 | Simple |
| Random Forest | 1.8 | 2.4 | Ensemble |
| XGBoost | 1.6 | 2.1 | Gradient Boosting |
| LSTM | 1.4 | 1.9 | Deep Learning |


## 🙏 Acknowledgments

### Libraries & Frameworks
- **[Flask](https://flask.palletsprojects.com/)** - Web framework by Pallets
- **[React](https://react.dev/)** - UI library by Meta
- **[Vite](https://vitejs.dev/)** - Build tool by Evan You
- **[scikit-learn](https://scikit-learn.org/)** - Machine learning library
- **[XGBoost](https://xgboost.readthedocs.io/)** - Gradient boosting framework
- **[TensorFlow](https://www.tensorflow.org/)** - Deep learning framework by Google
- **[Keras](https://keras.io/)** - High-level neural networks API
- **[pandas](https://pandas.pydata.org/)** - Data analysis library
- **[NumPy](https://numpy.org/)** - Numerical computing library
- **[yFinance](https://github.com/ranaroussi/yfinance)** - Yahoo Finance API wrapper
- **[Recharts](https://recharts.org/)** - Charting library for React
- **[Axios](https://axios-http.com/)** - HTTP client
- **[TextBlob](https://textblob.readthedocs.io/)** - Natural language processing
- **[BeautifulSoup4](https://www.crummy.com/software/BeautifulSoup/)** - Web scraping
- **[Matplotlib](https://matplotlib.org/)** - Plotting library
- **[Seaborn](https://seaborn.pydata.org/)** - Statistical visualization

### Data Sources
- **[Yahoo Finance](https://finance.yahoo.com/)** - Stock market data
- **[NewsAPI](https://newsapi.org/)** - News articles and headlines

### Inspiration & Resources
- Financial machine learning research papers
- Kaggle stock prediction competitions
- Time series forecasting methodologies
- Sentiment analysis in financial markets





## 🔮 Future Enhancements

- [ ] Real-time WebSocket updates
- [ ] Advanced portfolio optimization
- [ ] Technical indicators (RSI, MACD, etc.)
- [ ] Multi-timeframe analysis
- [ ] User authentication and saved portfolios
- [ ] Email alerts for price targets
- [ ] Mobile app (React Native)
- [ ] Cryptocurrency support
- [ ] Options pricing models

## ⚠️ Disclaimer

**This application is for educational and informational purposes only. It is not financial advice.**

- Stock predictions are based on historical data and machine learning models
- Past performance does not guarantee future results
- Always do your own research before making investment decisions
- Consult with a qualified financial advisor for investment advice
- The developers are not responsible for any financial losses


