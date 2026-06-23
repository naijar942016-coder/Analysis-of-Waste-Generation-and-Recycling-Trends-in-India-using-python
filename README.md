# Analysis-of-Waste-Generation-and-Recycling-Trends-in-India-using-python
This project focuses on analyzing waste generation and recycling patterns across India using Python. With rapid urbanization and population growth, waste management has become a major environmental challenge. 
# ♻️ Analysis of Waste Generation and Recycling Trends in India

## 📌 Project Overview
This project analyzes waste generation and recycling trends in India using Python. With increasing population and urbanization, waste management has become a major environmental issue. This project aims to explore waste generation patterns, evaluate recycling efficiency, and provide insights for sustainable waste management.

---

## 🎯 Objectives
- Analyze waste generation across India  
- Study recycling trends and efficiency  
- Identify high waste-generating regions  
- Perform data cleaning and preprocessing  
- Visualize trends using Python  

---

## 📊 Dataset Information
- Source: Government / Open Data (CPCB, Municipal Data, etc.)  
- File Name: `waste_management_india.csv`  
- Features may include:
  - State / City  
  - Year  
  - Waste Generated (tons)  
  - Waste Recycled (tons)  
  - Population  

---

## 🛠️ Technologies Used
- Python 🐍  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Jupyter Notebook  

---

## 🔍 Data Preprocessing
- Removed missing/null values  
- Converted data types (e.g., year, numeric values)  
- Renamed columns for better readability  
- Filtered irrelevant data  

---

## 📈 Exploratory Data Analysis (EDA)
- Year-wise waste generation trends  
- Recycling rate comparison  
- State-wise waste distribution  
- Waste vs population analysis  

---
##Dashboard
<details>
  <summary>Click to view Dashboard Screenshot</summary>
![Dashboard 1](final1.png)
![Dashboard 2](final2.png)
![Dashboard 3](final3.png)
</details>


## 📊 Sample Python Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv("waste_management_india.csv")

# Display data
print(df.head())

# Check missing values
print(df.isnull().sum())

# Convert Year column
df['Year'] = pd.to_datetime(df['Year'], format='%Y')

# Calculate recycling rate
df['Recycling Rate'] = (df['Waste Recycled'] / df['Waste Generated']) * 100

# Group by year
yearly_data = df.groupby('Year')['Waste Generated'].sum()

# Plot
yearly_data.plot(kind='line')
plt.title("Waste Generation Trend in India")
plt.xlabel("Year")
plt.ylabel("Waste Generated")
plt.show()
