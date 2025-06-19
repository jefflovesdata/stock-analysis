![2025-06-18_18-16-21 Stock Market Dashboard](https://github.com/user-attachments/assets/6ccea18d-f5dd-4766-8c3a-fc598b5f167f)
# Stock Market Data Analysis Using Python, SQL & Tableau

### Introduction

This project is an end-to-end demonstration of a data analysis pipeline. It begins with raw, historical stock market data for several major technology companies, processes it using Python, prepares it for a relational database, and culminates in a Tableau dashboard for visualization.

The primary goal is to take historical stock data for Apple, Facebook, Google, Nvidia, Tesla, and Twitter and perform the necessary cleaning, transformation, and feature engineering to make it suitable for robust analysis. The final output is an interactive dashboard that allows users to explore trends in stock volume, price changes, and moving averages.

### Methodology

The project followed a structured data analysis workflow:

1.  **Data Sourcing and Loading:** Historical daily trading data for each company was sourced from a Kaggle dataset. Each CSV file was loaded into a pandas DataFrame.
2.  **Exploratory Data Analysis (EDA):** Initial analysis was performed to understand the structure of the data, check for missing values, and analyze the distributions of key variables like closing price and volume.
3.  **Data Cleaning:** Data quality issues were addressed by handling missing values in 'Close' and 'Volume' columns using a forward-fill (`ffill`) method, converting the 'Date' column to a datetime object, and removing any duplicate rows.
4.  **Feature Engineering:** The datasets were enhanced by creating new features to support deeper analysis. This included:
    * Calculating 50-day and 200-day moving averages (`MA50`, `MA200`).
    * Creating lagged variables for the previous day's high, low, open, and close prices.
    * Engineering date-based features such as year, month, and day of the week.
5.  **Data Validation:** The transformed data was checked for integrity. This included verifying that no negative prices were present and that calculated features were within expected ranges. This step flagged a few instances of extreme volume changes that warranted further review.
6.  **SQL & Tableau Preparation:** All individual DataFrames were combined into a single, unified dataset. A `StockName` column was added to identify each security, and the final dataset was exported to a CSV file designed to be loaded into a SQL database. The final dashboard was then built in Tableau.

### Insights

* The initial EDA revealed that the datasets were largely consistent, though some had a small number of missing values in the 'Volume' column from their early trading history.
* The data validation process was crucial, as it identified two instances of extreme volume changes (over 5000%) in the Apple dataset that could represent significant market events or potential data anomalies requiring further investigation.

### Recommendations

Based on the analysis, several future steps could be taken to expand on this project:

* **Investigate Outliers:** A deeper analysis should be conducted on the extreme volume changes found in the Apple data to determine if they correspond to real-world events like stock splits or major news announcements.
* **Incorporate Advanced Modeling:** The engineered features (e.g., moving averages, lagged variables) provide a strong foundation for building predictive models. Time-series forecasting models like ARIMA or machine learning models could be developed to predict future stock movements.
* **Expand the Dataset:** To create an even richer analysis, other data sources could be integrated, such as market sentiment data from news headlines or social media, or macroeconomic indicators that could influence the tech sector.

### Final Dashboard

![Stock Market Analysis Dashboard](https://drive.google.com/uc?export=view&id=1cFbZTTXYDA0i5zOnG3Iaf3JxEOiftYKJ)

**[View the Interactive Dashboard on Tableau Public](https://public.tableau.com/views/StockMarketDashboard_17502922842120/StockMarketDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)** 
