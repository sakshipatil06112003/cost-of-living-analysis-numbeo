# cost-of-living-analysis-numbeo Data
This repository contains a complete data analysis workflow including web scraping cost of living data from the Numbeo website, cleaning and preprocessing the data, and performing exploratory data analysis (EDA) using Python. The project focuses on understanding cost of living patterns across cities and countries through meaningful visualizations.

# 🌍 Cost of Living Analysis Using Numbeo Data

##  Problem Statement

Comparing the cost of living across cities and countries is difficult due to multiple factors such as rent, groceries, restaurant prices, and purchasing power. Without structured data, individuals and organizations struggle to make informed decisions related to relocation, budgeting, and planning.


## 🎯 Objective

Perform Exploratory Data Analysis (EDA) on Numbeo cost of living data to:

* Compare living costs across cities and countries
* Understand the impact of rent, groceries, and purchasing power
* Identify major contributors to higher living expenses
* Observe trends across countries and years
* Present insights using clear visualizations

---

## 🛠 Step 1: Web Scraping

### Website Source

* **Numbeo** – https://www.numbeo.com/cost-of-living/rankings.jsp
### Tools Used - * Python, * Jupyter Notebook,  * Requests, * BeautifulSoup

**🔧 Process**
- Identified the data source and webpage structure.
- Extracted and structured the required data using Python.
- Cleaned and stored the data in CSV format for analysis.

### Scraping Code Snippet
```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

url = "https://www.numbeo.com/cost-of-living/rankings.jsp"
page = requests.get(url)

soup = BeautifulSoup(page.text, "html.parser")
```

## 🧹 Step 2: Data Cleaning

### Cleaning Steps

* Standardized column names
* Removed unwanted characters
* Converted data types
* Verified missing and duplicate values

### Cleaning Code Snippet

```python
df.columns = df.columns.str.lower().str.replace(" ", "_")

df.isnull().sum()
df.duplicated().sum()

df['cost_of_living_index'] = df['cost_of_living_index'].astype(float)
df['rent_index'] = df['rent_index'].astype(float)

df.to_csv("cleaned_cost_of_living.csv", index=False)
```


## 📊 Step 3: Exploratory Data Analysis (EDA)

### Numerical Features

* Cost of Living Index
* Rent Index
* Groceries Index
* Restaurant Price Index
* Local Purchasing Power Index

### Categorical Features

* City
* Country
* Year

---

## 📈 Step 4: Visualization

### Histogram Example

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.histplot(df['cost_of_living_index'], kde=True)
plt.title("Distribution of Cost of Living Index")
plt.show()
```

### Box Plot Example

```python
sns.boxplot(x=df['rent_index'])
plt.title("Box Plot of Rent Index")
plt.show()
```

## 🔍 Key Observations

* Rent strongly influences overall cost of living
* Grocery and restaurant prices are highly correlated with living costs
* Purchasing power does not always increase with higher expenses
* Some cities act as extreme outliers with very high costs

---

## 🔮 Future Enhancements

* Include more recent Numbeo data
* Perform continent-wise analysis
* Build interactive dashboards using Power BI or Tableau
* Apply clustering to group similar cities

---

## 👤 About Me

**Sakshi Pravin Patil**
Automation and Robotics Engineer | Aspiring Data Scientist

I come from an Automation and Robotics background and transitioned into Data Science after working on data-driven projects. This project demonstrates my ability to collect data through web scraping, clean and analyze it, and extract meaningful insights using visualization techniques.

🔗 LinkedIn: [https://www.linkedin.com/in/sakshi-patil-482245251](https://www.linkedin.com/in/sakshi-patil-482245251)
💻 GitHub: [https://github.com/sakshipatil06112003](https://github.com/sakshipatil06112003)

---

