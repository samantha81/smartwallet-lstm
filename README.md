# SmartWallet - Personal Finance Management System

SmartWallet is a Python-based personal finance management system designed to help users manage and analyze their personal finances from a single application.

The system allows users to track income and expenses, manage investments and loans, set financial goals, visualize spending patterns, and estimate future expenses using an LSTM-based machine learning model.

## Features

### 1. Account Management

* Register new accounts
* Login to existing accounts
* Store account data locally using JSON
* Automatic data loading and saving

### 2. Income & Expense Tracking

* Add and update income
* Record expenses by category
* Track historical expenses
* View current-month expense breakdowns
* Calculate current financial balance

### 3. Expense Prediction

SmartWallet uses an **LSTM (Long Short-Term Memory)** neural network to predict total expenses for the following month.

The prediction system:

* Uses historical expense data
* Applies Min-Max normalization to the input data
* Uses previous time steps as input sequences
* Trains an LSTM-based neural network using TensorFlow/Keras
* Predicts the estimated total expense for the next month
* Provides an estimated breakdown of expenses by category

> **Note:** At least six months of expense data is recommended for the prediction feature.

### 4. Financial Reports

Generate a financial report containing:

* Total income
* Total expenses
* Net balance
* Expense breakdown by category
* Investment summary
* Investment gains/losses
* Loan information

### 5. Expense Visualization

The application provides graphical representations of spending patterns using Matplotlib.

Available visualizations include:

* **Bar chart:** Current month's expenses by category
* **Line graph:** Total expenses over the previous six months

### 6. Investment Management

Users can manage multiple investments and record:

* Investment name
* Amount invested
* Current value
* Investment date
* Investment gain/loss

The system also calculates:

* Total amount invested
* Total current investment value
* Overall gain/loss

### 7. Loan Management

Users can:

* Add multiple loans
* View loan details
* Delete loans
* Calculate monthly loan payments
* Calculate total interest
* Generate loan amortization schedules
* View principal and interest paid for each month

### 8. Financial Goals

Users can create and manage financial goals.

Features include:

* Create multiple financial goals
* Set target amounts
* Track progress
* Update goal progress
* Delete goals
* Display progress as a percentage

### 9. Budget Planning

The system estimates the available budget for the following month based on:

* Current income
* Predicted expenses
* Saving targets
* Monthly loan payments

## Technologies Used

* **Python 3**
* **TensorFlow / Keras** - LSTM-based expense prediction
* **NumPy** - Numerical computation
* **Pandas** - Data processing
* **Matplotlib** - Data visualization
* **Tabulate** - Formatted tables
* **JSON** - Local data storage

## Project Structure

```text
SmartWallet/
│
├── main.py
├── data.json
└── README.md
```

> `data.json` is generated automatically when the application saves user data.

## Requirements

* Python 3.x
* pip

### Python Packages

```text
tensorflow
numpy
pandas
matplotlib
tabulate
```

## Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/smartwallet-personal-finance.git
```

2. Navigate to the project directory:

```bash
cd smartwallet-personal-finance
```

3. Install the required packages:

```bash
pip install tensorflow numpy pandas matplotlib tabulate
```

## Usage

Run the application with:

```bash
python main.py
```

### First-Time Users

Select:

```text
1. Register a new account
```

Then enter:

* Account ID
* Initial income

### Returning Users

Select:

```text
2. Login to existing account
```

Enter the registered account ID.

After logging in, users can access the following functions:

```text
1. Add more income
2. Add more expenses
3. Account information
4. Expenses prediction for next month
5. Financial report
6. Financial goals
7. Budget prediction for next month
8. Visualization
9. Investment
10. Loan
11. Back to main menu
```

## Data Storage

SmartWallet stores user information locally in:

```text
data.json
```

The application automatically loads existing data when started and saves updated information during relevant operations.

Example data categories include:

```text
Account
├── Income
├── Expenses
├── Investments
├── FinancialGoals
├── Predicted Expense
└── Loan
```

## Expense Prediction Model

The expense prediction component uses an LSTM neural network implemented with TensorFlow/Keras.

The model architecture consists of:

```text
Input
  ↓
LSTM (64 units)
  ↓
Dense (32 units)
  ↓
Dense (1 unit)
  ↓
Predicted Total Expense
```

The model uses:

* Adam optimizer
* Mean Squared Error (MSE) loss
* Mean Absolute Error (MAE) as an evaluation metric
* 10 training epochs
* Min-Max normalization

The model uses historical category-level expenses as input and predicts the total expense for the next month.

## Loan Calculation

For each loan, SmartWallet calculates:

* Monthly payment
* Total interest
* Total payment
* Payment end date
* Amortization schedule

The amortization schedule provides a monthly breakdown of:

| Month | Payment | Principal Paid | Interest Paid | Remaining Balance |
| ----- | ------: | -------------: | ------------: | ----------------: |
| 1     |   RM... |          RM... |         RM... |             RM... |
| 2     |   RM... |          RM... |         RM... |             RM... |

## Financial Goal Tracking

Each financial goal contains:

```text
Goal Name
Goal Amount
Current Progress
```

The application automatically calculates the completion percentage:

```text
Progress Percentage = Current Progress / Goal Amount × 100
```

## Security & Privacy

SmartWallet is designed as a local personal finance application.

* Financial data is stored locally.
* No external database is required.
* No cloud service is used for storing financial information.
* Data is stored in plain JSON format.

**Important:** The current implementation does not encrypt `data.json` and does not provide password-based authentication. Users should therefore protect access to the device and keep backups of important data.

## Limitations

* The application currently uses a command-line interface.
* Financial data is stored in a local JSON file.
* No encryption is implemented.
* The expense prediction model requires sufficient historical data.
* The machine learning prediction is intended as an estimate rather than professional financial advice.
* Expense prediction performance may vary depending on the amount and quality of historical data.
* Visualization features require a graphical environment.

## Best Practices

For better results, users should:

* Update income and expenses regularly.
* Categorize expenses consistently.
* Review financial reports periodically.
* Keep investment values up to date.
* Record loan information accurately.
* Update financial goal progress regularly.
* Back up `data.json` regularly.

## Disclaimer

SmartWallet is an educational software project for personal finance tracking and analysis. Its predictions and calculations should not be considered professional financial, investment, or lending advice.

## License

This project is available for educational and personal use.

