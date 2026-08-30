# EDA-SALES-DATA
# 📊 Sales Data Exploratory Data Analysis (EDA)

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on a Sales dataset to understand sales performance, customer segments, product categories, regional performance, profit, discounts, and delivery time.

The analysis is performed using **Python in Google Colab**, with libraries such as Pandas, NumPy, Matplotlib, and Seaborn.

The dataset contains **10,194 sales records and 21 columns** covering orders, customers, locations, products, sales, quantity, discount, and profit.

---

## 🎯 Objectives

The main objectives of this project are:

* Analyze the overall sales dataset.
* Understand sales and profit distribution.
* Analyze customer segments.
* Analyze product categories and sub-categories.
* Study regional sales performance.
* Examine the relationship between discount and profit.
* Analyze order and shipping information.
* Calculate delivery time using Order Date and Ship Date.
* Identify useful patterns and trends from the data.
* Visualize important business insights using charts.

---

## 🗂️ Dataset Information

The dataset contains the following major attributes:

| Column         | Description                     |
| -------------- | ------------------------------- |
| Row ID         | Unique row identifier           |
| Order ID       | Unique order identifier         |
| Order Date     | Date when the order was placed  |
| Ship Date      | Date when the order was shipped |
| Ship Mode      | Shipping method                 |
| Customer ID    | Customer identifier             |
| Customer Name  | Customer name                   |
| Segment        | Customer segment                |
| Country/Region | Country or region               |
| City           | Customer city                   |
| State/Province | Customer state or province      |
| Postal Code    | Postal code                     |
| Region         | Sales region                    |
| Product ID     | Product identifier              |
| Category       | Product category                |
| Sub-Category   | Product sub-category            |
| Product Name   | Name of the product             |
| Sales          | Sales amount                    |
| Quantity       | Quantity ordered                |
| Discount       | Discount applied                |
| Profit         | Profit generated                |

## The notebook converts `Order Date` and `Ship Date` into datetime values and creates a new `Delivery Days` feature by calculating the difference between shipping and order dates.

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Google Colab**
* **Jupyter Notebook**

---

## 🔍 EDA Process

### 1. Data Loading

The dataset is loaded into a Pandas DataFrame using:

```python
df = pd.read_csv("samplesuperstore.csv")
```

### 2. Data Understanding

The dataset structure is examined using:

```python
df.head()
df.info()
df.shape
df.describe()
```

The dataset contains 10,194 records and 21 original columns.

### 3. Data Type Conversion

The order and shipping dates are converted into datetime format:

```python
df['Order Date'] = pd.to_datetime(df['Order Date'], errors='coerce')
df['Ship Date'] = pd.to_datetime(df['Ship Date'], errors='coerce')
```

### 4. Feature Engineering

A new `Delivery Days` column is created:

```python
df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days
```

This helps analyze how long orders take to ship.

---

## 📈 Dataset Statistics

The numerical columns include:

* Sales
* Quantity
* Discount
* Profit

According to the notebook, the average values are approximately:

| Metric   | Average |
| -------- | ------: |
| Sales    |  228.23 |
| Quantity |    3.79 |
| Discount |   0.155 |
| Profit   |   28.67 |

The dataset also contains both positive and negative profit values, indicating that some sales transactions resulted in losses.

---

## 📊 Analysis Areas

The project focuses on analyzing:

### 🛍️ Product Analysis

* Sales by category
* Sales by sub-category
* Product performance
* Profit by product category

### 👥 Customer Analysis

* Customer segments
* Customer purchasing patterns
* Sales contribution by segment

### 🌎 Regional Analysis

* Sales by region
* Profit by region
* Regional performance comparison

### 💰 Profit & Discount Analysis

* Sales vs. profit
* Discount vs. profit
* Identification of loss-making transactions

### 🚚 Shipping Analysis

* Shipping modes
* Order dates
* Ship dates
* Delivery days

---

## 📊 Visualization

Matplotlib and Seaborn are used to create visualizations that make the sales patterns easier to understand.

Possible visualizations include:

* Bar charts
* Line charts
* Histograms
* Box plots
* Scatter plots
* Heatmaps

---

## 💡 Key Findings

The analysis shows that:

* The dataset contains **10,194 sales records**.
* Sales values vary significantly, ranging from **0.444 to 22,638.48**.
* Profit ranges from **-6,599.978 to 8,399.976**, showing both profitable and loss-making transactions.
* Discounts range from **0% to 80%**.
* Delivery time can be analyzed using the newly created `Delivery Days` column.

> **Note:** The notebook provides the data preparation and statistical analysis above. Specific claims about the *best-selling category, best region, or most profitable product* should only be added after those corresponding analyses are actually calculated.

---

## 📁 Project Structure

```text
Sales-Data-EDA/
│
├── Sales_Analysis_Colab.ipynb
├── samplesuperstore.csv
└── README.md
```

---

## ▶️ How to Run

### Option 1 — Google Colab

1. Open the notebook in Google Colab.
2. Upload `samplesuperstore.csv`.
3. Run the cells from top to bottom.
4. View the generated analysis and visualizations.

### Option 2 — Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

Then run:

```bash
jupyter notebook
```

Open:

```text
Sales_Analysis_Colab.ipynb
```

---

## 🚀 Future Improvements

The project can be improved by adding:

* Interactive dashboards using Power BI or Tableau.
* Monthly and yearly sales trend analysis.
* Top 10 products by sales and profit.
* Customer-level analysis.
* Regional performance dashboard.
* Correlation analysis.
* Outlier detection.
* Predictive sales forecasting.
* Machine learning for sales prediction.

---

## 👨‍💻 Author

**Mari Shankar**

This project was created as a Python-based **Exploratory Data Analysis (EDA)** project to analyze and visualize sales data.

---

## 📊 Output

The EDA produced the following results:

### Dataset Overview

* **Total Records:** 10,194
* **Original Columns:** 21
* **After Feature Engineering:** 22 columns
* **Numerical Columns:** Sales, Quantity, Discount, Profit
* **Date Columns:** Order Date, Ship Date
* **New Feature:** Delivery Days

The initial dataset contains 10,194 rows and 21 columns. After calculating delivery time, the dataset contains 22 columns.

### 📈 Statistical Output

| Metric  |    Sales | Quantity | Discount |   Profit |
| ------- | -------: | -------: | -------: | -------: |
| Mean    |   228.23 |     3.79 |    0.155 |    28.67 |
| Minimum |    0.444 |        1 |        0 | -6599.98 |
| Maximum | 22638.48 |       14 |      0.8 | 8399.976 |
| Median  |    53.91 |        3 |     0.20 |     8.69 |

These statistics come directly from the notebook's `df.describe()` output.

### 🔍 Data Processing Output

The project converts `Order Date` and `Ship Date` into datetime format and creates:

```python
df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days
```

Example delivery times from the processed data include **4 days** and **7 days**.

### 📊 Visual Output

The project generates visualizations to explore:

* Sales distribution
* Profit distribution
* Quantity distribution
* Discount distribution
* Category and sub-category performance
* Regional performance
* Customer segments
* Shipping information
* Delivery time

### 💡 Main Observation

The dataset contains both **positive and negative profit values**, showing that some transactions generate profit while others result in losses. The profit values range from **-6,599.978 to 8,399.976**.

> **Note:** The notebook data provided does not support claiming a specific “best-selling category” or “best region” without calculating those values. Do not put unsupported results in the README.


## ⭐ Conclusion

This project demonstrates how **Exploratory Data Analysis** can be used to transform raw sales records into meaningful business information. By analyzing sales, profit, customers, products, regions, discounts, and delivery time, organizations can better understand their sales performance and identify areas that require improvement.
