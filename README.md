# Supply Chain Delivery & Profitability Analysis

# Project Overview

This project analyzes supply chain and order fulfillment data from a global e-commerce business to understand delivery performance, identify operational bottlenecks, and investigate the relationship between shipping delays and profitability.

Using Python and Exploratory Data Analysis (EDA), the project examines order processing times, late deliveries, regional delivery performance, shipping modes, and profitability patterns.

The objective is to transform raw supply chain data into meaningful business insights that can support better shipping decisions, improve operational efficiency, and help reduce delivery delays.

# Business Problem

The business experiences inconsistent delivery performance across different regions. Actual shipping times sometimes exceed scheduled delivery timelines, creating operational challenges and potentially affecting order profitability.

This project investigates:

- How frequently do orders arrive later than scheduled?
- Which regions and operational categories experience higher delivery delay percentages?
- How does order profitability vary with delivery delays?
- Which shipping modes, customer segments, departments, and order types are associated with late deliveries?
- Are delivery delays associated with particular months, days of the week, or hours of the day?

# Project Objectives

- Clean and prepare supply chain data for analysis.
- Perform Exploratory Data Analysis (EDA).
- Calculate order processing time and delivery delays.
- Develop business KPIs for delivery performance and profitability.
- Analyze the relationship between delivery delays and order profitability.
- Identify potential delivery bottlenecks across operational categories.
- Investigate potential drivers of late deliveries by region.
- Analyze time-based patterns in delivery delays.
- Export the processed dataset for further analysis.

# Tools & Technologies

- **Python** — Data analysis and processing
- **Pandas** — Data manipulation, cleaning, and aggregation
- **NumPy** — Numerical operations and conditional calculations
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualization
- **Jupyter Notebook** — Interactive analysis and documentation

# 📂 Project Structure

```text
supply-chain-delivery-analysis/
│
├── supply_chain_analysis.ipynb
├── Supply_chain_analysis_report
├── supply_chain_cleaned.csv
└── README.md
```


# Project Workflow

# 1. Data Loading and Initial Exploration

- Load the supply chain dataset using Pandas.
- Inspect the dataset structure and column names.
- Examine missing values and duplicate records.
- Review categorical variables and their value distributions.

# 2. Data Cleaning and Preprocessing

- Remove selected columns that are not required for the analysis.
- Exclude records marked as shipping cancelled.
- Convert order and shipping dates into datetime format.
- Prepare the dataset for delivery performance and profitability analysis.

# 3. Feature Engineering

Create additional analytical features:

- **Order Processing Time:** Difference between the shipping date and order date, measured in days.
- **Delay:** Difference between actual processing time and scheduled shipment duration.
- **Is_Delayed:** Boolean indicator identifying orders whose calculated delay is greater than zero.
- **Order_month:** Month in which the order was placed.
- **Order_days:** Day of the week on which the order was placed.
- **Order_hour:** Hour at which the order was placed.
- **Profitability_Flag:** Classification of order profitability as Profit, Loss, or Break-even.

# 4. Business KPI Analysis

Calculate key performance indicators, including:

- Total orders in the analyzed dataset.
- Number of late deliveries.
- Late delivery percentage.
- On-time delivery percentage, based on the project's delay definition.
- 90th-percentile delay duration among delayed orders.
- Total positive order profit.
- Sum of order profit values associated with delayed orders.

**Note:** The last metric is the sum of order profit values for delayed orders. It should not automatically be interpreted as the actual financial loss caused by delays.

# 5. Profitability vs. Delivery Time Analysis

Investigate how order profit varies with delivery delay.

The analysis groups orders by calculated delay and examines:

- Average profit per order.
- Total order profit.
- Number of orders.
- Distribution of orders across delay durations.

Visualizations help compare delay frequency with profitability patterns.

# 6. Bottleneck Detection

Compare late delivery percentages across selected business categories:

- Order Region
- Customer Segment
- Shipping Mode
- Order Status
- Order Type
- Department Name

The analysis identifies categories with higher observed delay percentages for further investigation.

# 7. Root Cause Analysis

Examine potential drivers of late deliveries within a selected region.

The notebook evaluates:

- Shipping Mode
- Customer Segment
- Department Name
- Order Type
- Order Status

A reusable function calculates total orders, late orders, delay percentages, and average delay for each category. It then displays the ten category levels with the highest observed delay percentages.

These results indicate potential contributing factors rather than proving causation.

# 8. Time Series and Temporal Pattern Analysis

Investigate delivery delay percentages based on:

- Month of order placement.
- Day of the week.
- Hour of order placement.

Visualizations help identify periods with relatively high observed delivery delay percentages.

# 9. Exporting the Cleaned Dataset

The final notebook cell exports the processed DataFrame to a CSV file:

```python
df.to_csv('supply_chain_cleaned.csv', index=False)
```

The resulting file can be used for further analysis or as an input for a business intelligence dashboard.

# Key Analytical Outputs

The notebook generates visualizations and summary tables covering:

- Profitability distribution.
- Delivery delay distribution.
- Profit metrics by delay duration.
- Delay percentages across operational categories.
- Potential drivers of late delivery by region.
- Monthly delivery delay patterns.
- Delivery delays by day of the week.
- Delivery delays by order placement hour.

The notebook calculates these metrics from the loaded dataset. Numerical findings should be reported only after executing the notebook successfully and validating its outputs.

# How to Run the Project

# Step 1: Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/supply-chain-delivery-analysis.git
```

Replace `YOUR-USERNAME` with your GitHub username.

# Step 2: Navigate to the Project Folder

```bash
cd supply-chain-delivery-analysis
```

# Step 3: Install the Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

# Step 4: Add the Dataset

Place `DataCoSupplyChainDataset.csv` in the project directory, alongside the notebook.

The notebook expects this exact filename when loading the raw data.

# Step 5: Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `supply_chain_analysis.ipynb` and execute the cells sequentially.

**Important:** The notebook uses `display()` in its analysis sections. If you encounter a `NameError`, add the following import near the beginning of the notebook:

```python
from IPython.display import display
```

# Business Value

This analysis can help supply chain and operations teams:

- Monitor delivery performance using clearly defined KPIs.
- Identify regions and operational categories that require further investigation.
- Understand how profitability varies across delivery delay durations.
- Investigate recurring temporal patterns in delivery delays.
- Prioritize potential opportunities to improve shipping and fulfillment processes.
- Prepare a cleaned dataset for further reporting and dashboard development.

The findings are exploratory and should be validated with additional operational information before making major business decisions.

# Future Improvements

Potential next steps include:

- Develop an interactive Power BI dashboard.
- Add statistical tests to investigate differences in delivery performance.
- Build a machine learning model to predict late deliveries.
- Evaluate classification performance using precision, recall, F1-score, and ROC-AUC where appropriate.
- Investigate the effect of shipping mode, order characteristics, and regional factors on delivery performance.
- Develop recommendations based on validated analytical findings.

# Author

**Ankit Sardar**

Aspiring Data Analyst | Python | Excel | Power BI | Exploratory Data Analysis

---

*This project demonstrates practical data cleaning, feature engineering, KPI development, exploratory analysis, and data visualization using Python.*
