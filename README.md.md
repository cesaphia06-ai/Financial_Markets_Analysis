#  Financial Markets & Macroeconomic Indicators Analysis (2000–2008)

## Project Overview
This project analyzes historical financial and macroeconomic indicators from 2000 to 2008 to understand economic trends, assess market risk, and support informed decision-making in investment, policy, and research. The analysis covers the dot-com crash (2001) and the onset of the global financial crisis (2008), two of the most significant economic events of the period.

---

## Problem Statement
> *How can historical financial and macroeconomic indicators be analyzed and modeled to understand economic trends, assess market risk, and support informed decision-making in investment, policy, and research?*

---

## Dataset
- **Source:** Financial Markets & Macroeconomic Indicators Dataset
- **File:** `finance_economics_dataset.csv`
- **Period:** January 2000 – March 2008
- **Frequency:** Daily
- **Size:** 3,000 rows × 24 columns
- **Stock Indices covered:** S&P 500, NASDAQ, Dow Jones

### Key Variables
| Category | Variables |
|---|---|
| Stock Market | Open Price, Close Price, Daily High, Daily Low, Trading Volume |
| Macroeconomic | GDP Growth (%), Inflation Rate (%), Unemployment Rate (%), Interest Rate (%) |
| Consumer Metrics | Consumer Confidence Index, Retail Sales, Consumer Spending |
| Commodities | Crude Oil Price, Gold Price |
| Forex | USD/EUR, USD/JPY |
| Other | Government Debt, Corporate Profits, Bankruptcy Rate, M&A Deals, VC Funding |

---

## Project Structure
```
├── finance_economics_dataset.csv        # Dataset
├── Financial_Markets_Analysis.ipynb     # Main Colab notebook
└── README.md                            # Project documentation
```

---

## Tools & Libraries
| Library | Purpose |
|---|---|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical visualizations |
| `sklearn` | Machine learning models and preprocessing |
| `google.colab` | File upload in Google Colab |

---

## How to Run
1. Open [Google Colab](https://colab.research.google.com)
2. Upload the notebook `Financial_Markets_Analysis.ipynb`
3. Run the first cell and upload `finance_economics_dataset.csv` when prompted
4. Run all cells sequentially from top to bottom

---

## Analysis Sections

### 1. Descriptive Analytics (EDA)
Exploratory analysis of stock market trends, macroeconomic indicators, commodity prices, forex rates, trading volume, and statistical distributions.

### 2. Correlation Analysis
Investigation of relationships between key variables using a correlation heatmap and scatter plots of specific variable pairs.

### 3. Anomaly Detection
Identification of economic shocks and abnormal periods using the Isolation Forest algorithm.

### 4. Machine Learning Models
Prediction of stock Close Price using Linear Regression and Random Forest models, with performance comparison.

---

## Key Findings

### Descriptive Analytics
- All three stock indices (S&P 500, NASDAQ, Dow Jones) follow similar overall trends, driven by the same macroeconomic forces
- Visible dips are observed around 2001-2002 (dot-com crash) and 2007-2008 (financial crisis onset)
- The Dow Jones recorded the highest mean close price while S&P 500 recorded the lowest, reflecting differences in index construction
- Unemployment spiked during 2002-2003 and 2007-2008, corresponding to major economic downturns
- Inflation rose notably between 2006-2007 during a period of low unemployment and high consumer spending a classic pre-crisis boom
- Trading volume dipped sharply for NASDAQ and S&P 500 in 2002, reflecting significant loss of investor confidence
- Crude oil prices spiked sharply in 2005-2006, coinciding with the pre-crisis economic boom

### Correlation Analysis
- Stock price variables (Open Price, Close Price, Daily High, Daily Low, Trading Volume) are strongly intercorrelated (above 0.5) as expected
- Macroeconomic indicators show near zero correlations with each other and with stock prices, likely reflecting the interpolated and synthetic nature of the dataset
- The only meaningful relationship found among macro indicators is between Consumer Confidence Index and Retail Sales, which approaches linearity confirming that consumer sentiment drives spending behavior

### Anomaly Detection
- Isolation Forest (contamination=5%) identified 150 anomalous data points out of 3,000
- Anomalies are concentrated around 2000-2002 (dot-com crash) and 2005-2006 (pre-crisis boom)
- The model successfully flagged both the crash itself and the economic overheating that preceded the next crisis

### Machine Learning Models
| Model | RMSE | R² Score |
|---|---|---|
| Linear Regression | 16.31 | 0.9998 |
| Random Forest | 20.03 | 0.9997 |

- Both models achieved exceptional R² scores above 0.999
- Linear Regression slightly outperformed Random Forest, suggesting the relationship between features and Close Price is predominantly linear
- Note: High model performance is partly attributed to data leakage: Open Price, Daily High and Daily Low are included as features and are naturally highly correlated with Close Price

---

## Dataset Limitations
- Some macroeconomic indicators (GDP, inflation) are typically released quarterly, daily values are interpolated which may mask true relationships
- The dataset appears to be synthetic, which explains near zero correlations between macro indicators
- Global representation may be limited as data primarily reflects US economic indicators
- Missing values may occur on weekends and public holidays

---

## Conclusion
The analysis successfully covers all four required approaches: Descriptive Analytics, Correlation Analysis, Anomaly Detection and Machine Learning Modeling. The dataset captures two major economic events (dot-com crash and 2008 financial crisis onset) which are clearly visible across stock prices, trading volume, unemployment and commodity price trends. While macroeconomic indicator correlations are limited by the synthetic nature of the data, the Consumer Confidence vs Retail Sales relationship and the Isolation Forest anomaly detection results provide meaningful insights into the economic dynamics of the 2000-2008 period.
