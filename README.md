<h1 align="center">Fraud Detection System</h1>
<div align="center">
  <a href="https://python.org/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python"></a>
  <a href="https://scikit-learn.org/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white" alt="scikit-learn"></a>
  <a href="https://streamlit.io/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit"></a>
  <a href="https://pandas.pydata.org/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white" alt="pandas"></a>
  <a href="https://numpy.org/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white" alt="NumPy"></a>
  <a href="https://jupyter.org/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white" alt="Jupyter"></a>
  <a href="https://matplotlib.org/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/Matplotlib-11557c?logo=matplotlib&logoColor=white" alt="Matplotlib"></a>
  <a href="https://seaborn.pydata.org/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/Seaborn-3776AB?logo=seaborn&logoColor=white" alt="Seaborn"></a>
</div>

---

An intelligent machine learning system for detecting fraudulent financial transactions in real-time. Built with Python and scikit-learn, featuring a user-friendly Streamlit web interface for instant fraud detection predictions.

## Features

- **Real-time Fraud Detection** - Instant predictions on transaction legitimacy using trained ML models
- **Interactive Web Interface** - User-friendly Streamlit app for easy transaction analysis
- **High Accuracy Model** - 95% accuracy with 94% recall for fraud detection
- **Comprehensive Analysis** - Jupyter notebook with detailed model development and evaluation
- **Transaction Type Support** - Handles multiple transaction types (PAYMENT, TRANSFER, CASH_OUT, DEPOSIT, CASH_IN)
- **Balance Tracking** - Analyzes sender and receiver account balance changes

## Tech Stack

### Machine Learning

- **Python** - Core programming language
- **scikit-learn** - Machine learning library for model development
- **pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Logistic Regression** - Classification algorithm with balanced class weights

### Data Analysis & Visualization

- **Jupyter Notebooks** - Interactive data exploration and model development
- **Matplotlib** - Statistical data visualization
- **Seaborn** - Advanced statistical plotting

### Web Interface

- **Streamlit** - Interactive web application framework
- **Real-time Predictions** - Instant fraud detection via web interface

### Model Persistence

- **joblib** - Efficient model serialization and loading

## Model Performance

- **Accuracy**: 95%
- **Fraud Detection Recall**: 94%
- **Precision**: Optimized for fraud detection scenarios
- **Class Balancing**: Handles imbalanced datasets effectively

## Features Used for Prediction

### Transaction Details

- **Transaction Type** - PAYMENT, TRANSFER, CASH_OUT, DEPOSIT, CASH_IN
- **Amount** - Transaction amount in currency units
- **Sender Balance** - Old and new balance of the sender account
- **Receiver Balance** - Old and new balance of the receiver account

## Project Structure

```text
Fraud-Detection/
├── data/
│   └── AIML Dataset.csv
├── models/
│   └── fraud_detection_pipeline.pkl
├── notebooks/
│   └── analysis_model.ipynb
├── src/
│   └── fraud_detection.py
├── venv/
├── requirements.txt
└── README.md
```

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/Viper-Industries/fraud-detection.git
   cd fraud-detection
   ```

2. **Create virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Streamlit application**

   ```bash
   streamlit run src/fraud_detection.py
   ```

## Usage

### Web Interface

1. Launch the Streamlit app using the command above
2. Open your browser to the provided local URL (typically http://localhost:8501)
3. Enter transaction details:
   - Select transaction type from dropdown
   - Input transaction amount
   - Enter sender's old and new balance
   - Enter receiver's old and new balance
4. Click "Predict" to get instant fraud detection results

### Model Development

1. **Data Analysis**: Open `notebooks/analysis_model.ipynb` in Jupyter
2. **Model Training**: Run all cells to retrain the model with new data
3. **Model Evaluation**: Review classification reports and confusion matrices

## Model Details

### Algorithm
- **Logistic Regression** with balanced class weights to handle imbalanced fraud data

### Preprocessing Pipeline
- **StandardScaler** for numerical features (amounts and balances)
- **OneHotEncoder** for categorical features (transaction types)
- **Feature Engineering** removes unnecessary columns (names, flags, timestamps)

### Cross-Validation
- **Train/Test Split**: 70/30 with stratified sampling
- **Random State**: 42 for reproducible results

## Configuration

### Dependencies (requirements.txt)

```txt
pandas>=1.5.0
numpy>=1.21.0
scikit-learn>=1.1.0
joblib>=1.1.0
jupyter>=1.0.0
matplotlib>=3.5.0
seaborn>=0.11.0
streamlit>=1.28.0
```

## Data Requirements

The system expects a CSV file with the following columns:
- `step` - Time step of the transaction
- `type` - Transaction type (PAYMENT, TRANSFER, etc.)
- `amount` - Transaction amount
- `nameOrig` - Sender account identifier
- `oldbalanceOrg` - Sender's balance before transaction
- `newbalanceOrig` - Sender's balance after transaction
- `nameDest` - Receiver account identifier
- `oldbalanceDest` - Receiver's balance before transaction
- `newbalanceDest` - Receiver's balance after transaction
- `isFraud` - Target variable (0: legitimate, 1: fraud)
- `isFlaggedFraud` - System flag for large transactions

## Model Metrics

```
Classification Report:
              precision    recall  f1-score   support

           0       1.00      0.95      0.97   1906322
           1       0.02      0.94      0.04      2464

    accuracy                           0.95   1908786
   macro avg       0.51      0.94      0.51   1908786
weighted avg       1.00      0.95      0.97   1908786
```
