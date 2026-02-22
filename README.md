# Fraud Detection System

A machine learning-powered fraud detection system that uses classification algorithms to identify fraudulent transactions in real-time.

## Overview

This project implements a complet e fraud detection pipeline that analyzes transaction data and predicts whether a transaction is potentially fraudulent. The system includes data analysis, model training, and an interactive web application for making predictions.

## Features

- **Machine Learning Model**: Pre-trained classification model for fraud detection
- **Interactive Web App**: Streamlit-based user interface for real-time fraud prediction
- **Comprehensive Analysis**: Data exploration and visualization of transaction patterns
- **Multiple Transaction Types**: Support for PAYMENT, TRANSFER, CASH_OUT, and DEPOSIT transactions
- **Real-time Prediction**: Instant fraud classification based on transaction parameters

## Project Structure

```
fraud-detection/
├── fraud_detection.py              # Streamlit web application
├── analysis_method.ipynb           # Jupyter notebook with data analysis
├── fraud_detection_pipeline.pkl    # Pre-trained ML model
├── AIML Dataset.csv               # Transaction dataset
└── README.md                       # Project documentation
```

## Getting Started

### Prerequisites

- Python 3.7+
- pip (Python package installer)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/fraud-detection.git
cd fraud-detection
```

2. Install required packages:
```bash
pip install streamlit pandas scikit-learn joblib
```

### Usage

#### Running the Web Application

Start the Streamlit app to make fraud predictions:

```bash
streamlit run fraud_detection.py
```

The application will open in your browser at `http://localhost:8501`

**Input Parameters:**
- **Transaction Type**: Select from PAYMENT, TRANSFER, CASH_OUT, or DEPOSIT
- **Amount**: Transaction amount in currency units
- **Old Balance (Sender)**: Sender's account balance before transaction
- **New Balance (Sender)**: Sender's account balance after transaction
- **Old Balance (Receiver)**: Receiver's account balance before transaction
- **New Balance (Receiver)**: Receiver's account balance after transaction

#### Data Analysis

Review the analysis and data exploration:

```bash
jupyter notebook analysis_method.ipynb
```

This notebook contains:
- Data loading and exploration
- Transaction type distribution analysis
- Fraud rate analysis by transaction type
- Data quality assessment

## Dataset

The project uses the **AIML Dataset.csv** containing transaction records with the following features:

- `type`: Transaction type (PAYMENT, TRANSFER, CASH_OUT, DEPOSIT)
- `amount`: Transaction amount
- `oldbalanceOrg`: Sender's initial balance
- `newbalanceOrig`: Sender's balance after transaction
- `oldbalanceDest`: Receiver's initial balance
- `newbalanceDest`: Receiver's balance after transaction
- `isFraud`: Target variable (1 = fraudulent, 0 = legitimate)
- `isFlaggedFraud`: Fraud flag indicator

## Model

The fraud detection system uses a pre-trained machine learning pipeline (`fraud_detection_pipeline.pkl`) that has been optimized for detecting fraudulent transactions with high accuracy.

**Model Input:** Transaction features (type, amount, balances)  
**Model Output:** Binary classification (0 = legitimate, 1 = fraudulent)

## Results

The model provides real-time predictions with visual feedback:
- ✅ **Green message**: Transaction is legitimate
- ❌ **Red message**: Transaction is flagged as potential fraud

## **Real-World Use Cases**

- **Banking Transaction Monitoring**: Automatically flag suspicious transfers and payments to reduce losses and trigger investigations.
- **E-commerce Payment Fraud Prevention**: Detect and block risky online payments (stolen cards, account takeovers) during checkout.
- **Credit Card Fraud Detection**: Monitor cardholder transactions in real-time to identify unusual patterns and decline fraudulent charges.
- **Anti-Money Laundering (AML) Support**: Serve as a component in AML pipelines to highlight high-risk transactions for further review.
- **Insurance Claim Fraud Screening**: Help identify anomalous claim payments and suspicious payout patterns.
- **Fintech Risk Scoring & Onboarding**: Assess transaction histories and initial transfers to flag high-risk accounts during onboarding.
- **Merchant Risk Assessment**: Evaluate incoming transaction flows to detect merchants with abnormal refund/chargeback behaviors.
- **Customer Support Triage**: Provide fast fraud signals to prioritize support tickets and reduce investigation time.
- **Real-time Blocking & Alerts**: Integrate with transaction processing systems to block or alert on high-risk transactions instantly.
- **Analytics & Reporting**: Aggregate flagged cases for trend analysis, compliance reporting, and model improvement.

## Technologies Used

- **Python**: Core programming language
- **Streamlit**: Web application framework
- **Pandas**: Data manipulation and analysis
- **Scikit-learn**: Machine learning algorithms
- **Joblib**: Model serialization
- **Jupyter**: Interactive data analysis

## Future Enhancements

- [ ] Add model retraining pipeline with new data
- [ ] Implement advanced feature engineering
- [ ] Add transaction history tracking
- [ ] Develop alert system for high-risk transactions
- [ ] Create model performance dashboard
- [ ] Implement A/B testing for model improvements

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For questions or suggestions, please open an issue on GitHub.

---

**Note**: This system should be used as one component of a comprehensive fraud detection strategy and should not be the sole basis for financial decisions.
