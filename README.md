# Trader Performance vs Bitcoin Market Sentiment Analysis

This repository contains a Jupyter Notebook that analyzes the relationship between Hyperliquid trader performance and Bitcoin Fear/Greed market sentiment.

## Project Overview

The goal of this project is to investigate how different Bitcoin market sentiment phases (Fear, Greed, Neutral) impact the trading performance of Hyperliquid users. The analysis covers overall performance, long vs. short trade effectiveness, top/bottom traders, symbol-specific patterns, and time-based trading behaviors.

## Datasets

Two primary datasets are used:

1.  `historical_data.csv`: Contains detailed historical trading data from Hyperliquid, including execution prices, trade sizes, PnL, fees, and timestamps.
2.  `fear_greed_index.csv`: Provides historical Bitcoin Fear & Greed Index values, classifications (e.g., Extreme Fear, Greed), and timestamps.

## Methodology

The analysis follows these key steps:

1.  **Data Loading and Initial Inspection**: Both `historical_data.csv` and `fear_greed_index.csv` are loaded into pandas DataFrames.
2.  **Column Cleaning**: Column names are standardized for easier access and consistency.
3.  **Data Type Conversion**: Timestamps are converted to datetime objects, and relevant numeric columns are converted to appropriate data types. Missing values in critical columns are handled by dropping corresponding rows.
4.  **Data Merging**: The trader performance data is merged with the sentiment data based on the `date` column. A `broad_sentiment` category (Fear, Greed, Neutral) is created.
5.  **Performance Metrics Calculation**: New columns such as `is_win` (indicating profitable trades), `day_of_week`, `hour`, and `netPnL` are derived.
6.  **Exploratory Data Analysis (EDA)**:
    *   **Overall Performance by Sentiment**: Total trades, total PnL, average PnL, median PnL, and win rates are calculated and visualized for each broad sentiment category.
    *   **Long vs. Short Performance by Sentiment**: A detailed breakdown of performance metrics for BUY (Long) and SELL (Short) trades within each sentiment phase.
    *   **Top and Bottom Traders**: Traders are ranked by their total PnL.
    *   **Symbol-wise Patterns**: Analysis of performance for different trading symbols (`@107`, `wBTC`, `ETH`, etc.) across sentiment categories.
    *   **Leverage/Trade-size Behavior**: Examination of average leverage and trade size in relation to sentiment (if leverage data is available).
    *   **Time-based Trading Patterns**: Performance analysis by day of the week.
7.  **Insights and Recommendations**: Key findings are summarized, and actionable trading recommendations are provided based on the analysis.
8.  **Output Export**: Summarized dataframes (`merged_trader_sentiment.csv`, `sentiment_performance_summary.csv`, `trader_performance_summary.csv`) are saved as CSV files.

## Key Findings

*   **Best Average PnL is during: Fear**: Traders, on average, experienced higher PnL during periods of 'Fear' sentiment.
*   **Worst Average PnL is during: Neutral**: 'Neutral' sentiment periods were associated with the lowest average PnL.
*   **Highest Win Rate is during: Fear**: The highest win rate was also observed during 'Fear' market sentiment.
*   **Long vs. Short Discrepancies**: Performance metrics for BUY and SELL trades vary significantly across different sentiment categories, indicating that sentiment impacts long and short strategies differently.
*   **Day of Week Patterns**: There are observable differences in average PnL across different days of the week, with Saturday showing the highest average PnL and Sunday the lowest.

## Trading Recommendations

*   **Study Strategies During Fear**: Traders should analyze successful strategies employed during 'Fear' market phases, as these periods yielded the highest average PnL and win rates.
*   **Exercise Caution During Neutral Sentiment**: Be more conservative or adjust strategies during 'Neutral' sentiment, as this phase showed the lowest average PnL.
*   **Differentiate Long and Short Analysis**: Always compare long and short trades separately, as market sentiment can have distinct effects on each.
*   **Monitor Position Size/Leverage**: Pay close attention to position sizing and leverage during emotional market phases like 'Fear' and 'Greed', as these can amplify both gains and losses.
*   **Focus on Holistic Performance**: When evaluating traders or symbols, prioritize those with both a high win rate and positive total PnL, rather than solely focusing on the number of trades.

## Installation and Usage

1.  Clone this repository:
    ```bash
    git clone https://github.com/PragnaChowdary15/trader_sentiment_analysis/
    cd trader_sentiment_analysis
    ```
2.  Install the required Python packages:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
3.  Place `historical_data.csv` and `fear_greed_index.csv` in the root directory of the cloned repository.
4.  Open and run the Jupyter Notebook

Feel free to explore the notebook, modify the code, and extend the analysis!
```
