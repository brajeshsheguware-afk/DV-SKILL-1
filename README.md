# Superstore Sales Data Analysis

## 📌 Project Overview

This project focuses on understanding, preprocessing, and analyzing the **Superstore Sales dataset** using Python.

The project includes data cleaning, statistical analysis, date conversion, delivery time calculation, category analysis, and Exploratory Data Analysis (EDA). Different visualizations are used to understand sales, profit, discount, and relationships between numerical variables.

The analysis was performed using **Google Colab**.

---

## 🎯 Objectives

* Understand the structure of the Superstore Sales dataset
* Inspect and clean the dataset
* Convert date columns into proper datetime format
* Calculate delivery days for each order
* Check for missing values
* Analyze sales and profit performance
* Study the effect of discounts on profit
* Identify important correlations
* Create meaningful data visualizations
* Extract useful business insights from the dataset

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Google Colab**
* **Google Drive**

---

## 📂 Dataset

**Dataset Name:** `samplesuperstore.csv`

The dataset contains:

* **10,194 records**
* **21 columns**

### Main Columns

* Row ID
* Order ID
* Order Date
* Ship Date
* Ship Mode
* Customer ID
* Customer Name
* Segment
* Region
* Category
* Sub-Category
* Product Name
* Sales
* Quantity
* Discount
* Profit

---

# 📌 Task 1 – Data Understanding & Preprocessing

## 1. Importing Libraries

Pandas and NumPy were imported for data processing and analysis.

```python
import pandas as pd
import numpy as np
```

---

## 2. Loading the Dataset

The `samplesuperstore.csv` file was loaded into a Pandas DataFrame.

```python
df = pd.read_csv("/content/drive/MyDrive/samplesuperstore.csv")
```

---

## 3. Dataset Inspection

The dataset structure was examined using:

```python
df.head()
df.info()
```

This helped to understand the columns, data types, number of records, and non-null values.

---

## 4. Statistical Analysis

The `describe()` function was used to obtain statistical information about numerical columns.

```python
df.describe()
```

This provides information such as:

* Count
* Mean
* Standard deviation
* Minimum value
* Maximum value
* Quartiles

---

## 5. Date Conversion

The `Order Date` and `Ship Date` columns were converted into datetime format.

```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])
```

This makes date-based calculations and analysis easier.

---

## 6. Delivery Days Calculation

A new column named `Delivery Days` was created.

```python
df['Delivery Days'] = (
    df['Ship Date'] - df['Order Date']
).dt.days
```

This column represents the number of days taken between the order date and shipping date.

---

## 7. Category Analysis

The unique product categories were identified using:

```python
df['Category'].unique()
```

The dataset contains three major categories:

* Furniture
* Office Supplies
* Technology

---

## 8. Missing Value Analysis

Missing values were checked using:

```python
df.isnull().sum()
```

### Result

No missing values were found in the dataset.

---


