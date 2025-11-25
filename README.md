# Exploratory-Data-Analysis-With-Python-and-Numpy-Pandas-Seaborn-Matplotlib-

This repository contains my implementation of the Coursera guided project  
**“Exploratory Data Analysis With Python and Pandas”**.

The project performs end-to-end **Exploratory Data Analysis (EDA)** on a
**supermarket retail sales dataset**, using Python, Pandas, NumPy, Seaborn and
Matplotlib.  
The goal is to explore the data, clean it, visualise patterns and understand
what drives sales and customer behaviour.

---

## 🧾 Dataset

- **Source:** Kaggle – *Supermarket Sales* dataset  
- **Rows:** 1,003 transactions  
- **Columns:** 17 features  
- **Time range:** January 2019 – March 2019  
- **Granularity:** Each row = one customer transaction

**Key columns**

- `Invoice ID` – unique invoice identifier  
- `Branch` – store branch (A, B, C)  
- `City` – city where the branch is located  
- `Customer type` – Member / Normal  
- `Gender` – Male / Female  
- `Product line` – product category (Health and beauty, Fashion accessories, etc.)  
- `Unit price`, `Quantity`, `Tax 5%`, `Total` – transactional financials  
- `Date`, `Time` – when the purchase was made  
- `Payment` – payment method (Cash, Credit card, Ewallet)  
- `cogs`, `gross margin percentage`, `gross income` – profitability metrics  
- `Rating` – customer satisfaction rating (1–10)

In this repo, the raw CSV is stored as:
data/supermarket_sales.csv

---

## 🎯 Project Objectives

This project focuses on three main learning objectives:
- Apply practical EDA techniques on a tabular dataset using Python.
- Produce visualisations with Seaborn and Matplotlib.
- Identify and handle duplicate and missing data in a structured way.

---

## 🧠 EDA Workflow

All analysis is done in the notebook:
notebooks/Learner_Notebook.ipynb
The notebook is organised into the following tasks, following the Coursera
project structure.

**Task 1 – Initial Data Exploration**
Imported core libraries: Pandas, NumPy, Seaborn, Matplotlib.
Loaded supermarket_sales.csv and inspected:
First few rows with head()
Shape and data types with info()
Summary statistics with describe()
Performed quick checks on:
Unique values for categorical columns
Basic date range and time coverage

**Task 2 – Univariate Analysis**
Analysed continuous variables (e.g. Unit price, Quantity, Rating,
gross income) using:
Histograms
Kernel Density Estimation (KDE) plots
Analysed categorical variables (e.g. Branch, Payment,
Product line, Customer type, Gender) using:
Count plots to compare category frequencies
Overlayed mean, 25th and 75th percentiles on the customer rating
distribution to understand central tendency and spread.

**Task 3 – Bivariate Analysis**
Investigated relationships between numeric variables:
Scatter and regression plots of Rating vs gross income
Compared sales across categories:
Boxplots of Total / gross income by Branch
Sales comparison between Gender groups
Explored time patterns:
Time-series line plots of gross income over three months
Simple calendar-style view of daily income to highlight busy days

**Task 4 – Handling Duplicates & Missing Values**
Checked for duplicate rows with duplicated() and removed them where
necessary.
Inspected missing values with isnull().sum().
Handled missing numeric values by imputing the column mean rather than
simply dropping rows.
Demonstrated how Pandas Profiling can be used to automatically generate
an EDA report (where environment allows).

**Task 5 – Correlation Analysis**
Selected numeric columns and calculated:
Pairwise correlations using df.corr()
Individual correlations using NumPy
Visualised the correlation matrix as a heatmap using Seaborn.
Interpreted relationships between monetary variables such as:
Quantity, Unit price, Total, cogs, Tax 5%, gross income
Weak relationship between Rating and revenue metrics.

## 📈 Key Visualisations

The image below summarises several key EDA outputs:

https://yocddozasimw.labs.coursera.org/files/logo.png?_xsrf=2%7C6de779d5%7C31bf7e96160acfbc0d3818a93d2e6f22%7C1761826112

**Top-left: Distribution of customer ratings with KDE curve.**
The dashed red line marks the mean rating, and the green dashed lines
indicate the 25th and 75th percentiles, showing that most customers rate
their experience around ~7 on a 1–10 scale.

**Bottom-left: A calendar-style heatmap**
of daily performance across the
three months, highlighting days with higher sales or activity.

**Right: A correlation heatmap of numeric variables.**
Strong positive correlations appear between:
Quantity, Total, cogs, gross income and Tax 5%
While Rating is almost uncorrelated with revenue metrics, suggesting that
higher income days are not necessarily driven by higher reported satisfaction.

---

## 🔍 Selected Insights
Some example findings from the analysis:
The dataset covers 1,003 transactions across 3 branches over roughly
three months (Jan–Mar 2019).
The average customer rating is approximately 7.0 / 10, indicating
generally positive satisfaction.
Branches A, B and C have a fairly balanced number of transactions, with
Branch A slightly ahead.
Fashion accessories is the most frequently purchased product line.
Monetary variables (Total, cogs, Tax 5%, gross income, Quantity,
Unit price) are strongly positively correlated, as expected.
Rating shows very weak correlation with gross income, suggesting that
sales volume and satisfaction do not move together in a simple linear way.

---

## 🛠️ Tech Stack

Language: Python 3
Environment: Jupyter Notebook
Libraries:
pandas
numpy
seaborn
matplotlib
(optional) pandas-profiling / ydata-profiling
