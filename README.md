# 📊 Trader Performance vs Market Sentiment 

Analyzing how Bitcoin market sentiment (Fear/Greed) relates to trader behavior and performance on Hyperliquid.

---

##  Project Structure
```
├── primetrade_analysis.ipynb   # Main analysis notebook
├── historical_data.csv         # Hyperliquid trader data (not included)
├── fear_greed_index.csv        # Bitcoin Fear/Greed index (not included)
└── README.md
```

---

##  Setup
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

---

##  How to Run

1. Clone the repo
```bash
git clone 
cd 
```

2. Add your datasets to the same folder:
   - `historical_data.csv`
   - `fear_greed_index.csv`

3. Open and run the notebook:
```bash
jupyter notebook primetrade_analysis.ipynb
```

> Run `Kernel → Restart & Run All`

---

##  What the Notebook Covers

### Part A — Data Preparation
- Dataset audit: rows, columns, missing values, duplicates
- Timestamp conversion & date alignment
- Key metrics: daily PnL, win rate, leverage distribution, trade count, long/short ratio

### Part B — Analysis
- Fear vs Greed performance comparison (PnL, win rate, drawdown proxy)
- Statistical significance testing (Mann-Whitney U)
- Behavior shifts by sentiment: leverage, trade frequency, long/short bias
- 3 trader segments: High/Low Leverage · Frequent/Infrequent · Consistent Winners

### Part C — Strategy Recommendations
- 3 actionable trading rules backed by data

### Bonus
- Random Forest model predicting next-day trader profitability — achieved **89% accuracy** (F1-score: 0.89)
- K-Means clustering into 4 behavioral archetypes
- PCA visualization of trader clusters

---

##  Output Charts

| Chart | Description |
|-------|-------------|
| `chart_pnl_sentiment.png` | Avg PnL & win rate by Fear/Greed |
| `chart_behavior_sentiment.png` | Leverage, frequency, long ratio by sentiment |
| `chart_segments.png` | 3 segments × sentiment PnL comparison |
| `chart_insight1_timeseries.png` | PnL time-series coloured by sentiment |
| `chart_insight2_leverage_pnl.png` | Leverage vs PnL scatter |
| `chart_insight3_long_ratio.png` | Long/short bias by sentiment |
| `chart_insight4_heatmap.png` | Heatmap: sentiment × leverage segment |
| `chart_model.png` | Confusion matrix + feature importance |
| `chart_clusters.png` | Trader archetypes (PCA 2D) |

---

##  Key Insights

1. **Fear days reduce win rates and PnL** — traders overtrade and over-leverage during market stress
2. **High-leverage traders suffer most on Fear days** — clearly visible in the sentiment × leverage heatmap
3. **Persistent long bias hurts on Fear days** — traders maintain >50% long ratio even when sentiment is negative
4. **Consistent winners are more resilient** — smaller PnL drop on Fear days, indicating better risk management

---

##  Strategy Recommendations

| # | Rule |
|---|------|
| 1 | **Fear = De-risk** → High-leverage traders should cap leverage at 50% on Fear days |
| 2 | **Greed = Selective aggression** → Only consistent winners should increase activity on Greed days |
| 3 | **Reduce long bias on Fear days** → Shift at least 20% of long exposure to neutral/short |

---

##  Tech Stack

`Python` · `Pandas` · `NumPy` · `Scikit-learn` · `Matplotlib` · `Seaborn` · `SciPy`

