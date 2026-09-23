# Bitcoin Historical Market Intelligence & Price Trend Prediction

An end-to-end Data Analytics, Business Intelligence, and Predictive Machine Learning project submitted for the AICTE | IBM SkillsBuild Internship Program (conducted by BharatCares in association with AICTE).

---

## 1. Project Overview
Financial and cryptocurrency markets generate massive, high-frequency transaction logs that are difficult to convert into strategic business decisions. This project transforms granular, tick-level Bitcoin trading data into daily aggregated candles to build a complete 5-tier Business Intelligence (BI) and predictive analytics decision pipeline:
1. **Level 1 (KPIs):** Monitoring core financial valuation metrics, trailing returns, drawdowns, and annualized rolling volatility.
2. **Level 2 (Trends):** Tracking macro momentum using 20-day and 50-day Simple Moving Averages (SMA) and identifying crossover signals.
3. **Level 3 (Drivers):** Analyzing the correlation between aggregated daily trading volumes and price variance to spot liquidity drivers.
4. **Level 4 (Risk & Predictive Modeling):** Training a supervised Random Forest Classifier to forecast next-day directional movement (Up vs. Down).
5. **Level 5 (Actionable Strategies):** Implementing programmatic risk-off rules and automated Dollar-Cost Averaging (DCA) mechanisms.

---

## 2. Dataset Information
- **Dataset Name:** [Bitcoin Historical Data](https://www.kaggle.com/datasets/mczielinski/bitcoin-historical-data)
- **Primary Source:** Kaggle (Bitstamp BTC/USD Exchange Data)
- **Granularity & Structure:** 1-minute interval transaction feeds (`Timestamp`, `Open`, `High`, `Low`, `Close`, `Volume_BTC`, `Volume_USD`, `Weighted_Price`) resampled into daily OHLCV bars.
- **Preprocessing:** Conversion of Unix timestamps to UTC datetimes, forward-filling of zero-trade volume gaps, and daily resampling to prevent memory exhaustion and align with strategic time horizons.

---

## 3. Technologies Used
- **Programming Language:** Python 3.x
- **Development Environment:** Jupyter Notebook (`.ipynb`)
- **Data Manipulation & Analysis:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning & Evaluation:** Scikit-learn (`RandomForestClassifier`, `train_test_split`, `accuracy_score`, `classification_report`, `confusion_matrix`)

---

## 4. Setup & Running Instructions

### Prerequisites
Ensure Python 3.8+ and `pip` are installed on your system.

### Step 1: Clone the Repository
```bash
git clone [https://github.com/rameswarbehera00/bitcoin-market-analytics-prediction.git](https://github.com/rameswarbehera00/bitcoin-market-analytics-prediction.git)
cd bitcoin-market-analytics-prediction
Step 2: Install Required DependenciesInstall the required packages using the provided requirements.txt:Bashpip install -r requirements.txt
Step 3: Dataset Configuration (Optional)Download btcusd_1-min_data.csv from Kaggle and place it directly into the project directory.Note: If the large CSV is not present locally, the notebook includes an automated synthetic baseline generator that initializes time-series parameters so all code cells, metrics, and visual plots execute seamlessly without errors.Step 4: Run the AnalysisLaunch Jupyter Notebook or VS Code and execute the notebook:Bashjupyter notebook Rameswar_BitcoinAnalytics.ipynb
Select Run All Cells to view the inline KPI metrics, data tables, exploratory distribution charts, and model evaluation reports.5. Key Findings & Strategic InsightsExecutive Market KPIs (Level 1)Latest Close Valuation: Establishes benchmark asset pricing.Drawdown from All-Time High (ATH): Quantifies capital impairment from peak levels:$$\text{Drawdown (\%)} = \frac{\text{Latest Close} - \text{ATH}}{\text{ATH}} \times 100 \approx -31.56\%$$30-Day Trailing Return: Demonstrates medium-term price momentum (+10.04%).Annualized 30-Day Volatility: Measures market turbulence ($\approx 43.28\%$).Technical Trends & Market Drivers (Levels 2 & 3)Moving Average Trends: Golden crosses (20-day SMA crossing above 50-day SMA) confirm sustained multi-week upward momentum, while price breakdowns below the 50-day SMA signal impending consolidation.Volume vs. Return Distribution: Extreme daily percentage swings correlate with volume spikes, whereas steady price accumulation occurs during lower-volume consolidation bands.Predictive Model Performance (Level 4)Model Architecture: Random Forest Classifier (100 estimators, max depth = 6).Validation Scheme: Chronological time-series split (80% training set, 20% hold-out test set) to prevent look-ahead bias.Directional Classification Accuracy: Achieved balanced directional accuracy ($\approx 49\% - 53\%$) with detailed precision, recall, and confusion matrix outputs, consistent with financial market benchmarks under efficient market hypothesis conditions.Strategic Action Plan (Level 5)Capital Preservation Trigger: When 30-day annualized volatility exceeds 65%, portfolio allocation algorithms switch to risk-off asset preservation.Accumulation Trigger: Automated Dollar-Cost Averaging (DCA) is initiated during low-volatility accumulation bands when prices hold above the 50-day SMA.Stop-Loss Execution: Trailing stop-loss orders are dynamically triggered whenever daily close prices drop below the 50-day moving average.6. Repository File StructurePlaintextbitcoin-market-analytics-prediction/
├── .gitignore                          # Ignores large CSV files, cache, and virtual environments
├── LICENSE                             # MIT Open Source License
├── README.md                           # Comprehensive project documentation
├── requirements.txt                    # Project dependencies and library versions
├── Rameswar_BitcoinAnalytics.ipynb     # Fully executed Jupyter Notebook with inline visualizations
└── Rameswar_ProjectReport.docx         # Formal Word project report with embedded charts
7. Author InformationCandidate Name: Rameswar BeheraBranch / Specialization: Computer Science and EngineeringInstitution: Indira Gandhi Institute of Technology, Sarang, Odisha (PIN: 759146)Program: AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026 (BharatCares)GitHub Profile: @rameswarbehera00