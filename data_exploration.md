# EXP:1	EXP 1: Data Exploration

## Aim:
To import, clean, and explore datasets using Python and visualize data to interpret patterns effectively.
## Tools Required:
Python (Pandas, Matplotlib, Seaborn)
Excel
Optional: Tableau
## Procedure
## Part A: Importing and Cleaning Data

## 1.Load Datasets
```
Import libraries.
Load datasets in CSV and Excel formats.
Display the first few rows to verify data.
```
## code:
```
import pandas as pd
# Load CSV file
csv_file_path = 'sample_data.csv'
csv_data = pd.read_csv(csv_file_path)
# Load Excel file
excel_file_path = 'sample_data.xlsx'
excel_data = pd.read_excel(excel_file_path)
# Display the first few rows of the datasets
print("CSV Data:\n", csv_data.head())
print("\nExcel Data:\n", excel_data.head())
```
## 2.Handle Missing Values
```
Replace missing values with default values or calculated metrics.
Alternatively, drop rows with missing data.
```
## code:
```
data = {'Name': ['Alice', 'Bob', 'Charlie', None],
        'Age': [25, None, 30, 29],
        'Salary': [50000, 54000, None, 58000]}
df = pd.DataFrame(data)
print("Original Data:\n", df)
# Fill missing values
df_filled = df.fillna({'Name': 'Unknown', 'Age': df['Age'].mean(), 'Salary': df['Salary'].median()})
print("\nData after Filling Missing Values:\n", df_filled)
# Drop rows with missing values
df_dropped = df.dropna()
print("\nData after Dropping Rows with Missing Values:\n", df_dropped)
```
## 3.Perform Basic Data Exploration
```
Calculate mean, median, and mode for key columns.
```
## code:
```
mean_age = df['Age'].mean()
median_salary = df['Salary'].median()
mode_name = df['Name'].mode()[0]
print("\nBasic Data Exploration:")
print(f"Mean Age: {mean_age}")
print(f"Median Salary: {median_salary}")
print(f"Mode of Name: {mode_name}")
```
## Sample Outputs(Based on Example data):
![image](https://github.com/user-attachments/assets/b860dea1-c527-4179-9846-59e0ab0a3a77)

## Part B: Visualization Basics
```
1.Prepare Data and Import Libraries

Set up example data.
```
## code:
```
import matplotlib.pyplot as plt
import seaborn as sns
data = {'Category': ['A', 'B', 'C', 'D'], 'Values': [15, 30, 45, 10], 'Time': ['2021', '2022', '2023', '2024'], 'Growth': [100, 120, 150, 200]}
df = pd.DataFrame(data)
```
## 2.Bar Chart
```
Used to compare categorical data.
```
## code:
```
plt.figure(figsize=(8, 5))
sns.barplot(x='Category', y='Values', data=df, palette='viridis')
plt.title('Bar Chart of Values by Category', fontsize=16)
plt.xlabel('Category', fontsize=12)
plt.ylabel('Values', fontsize=12)
plt.show()
```
## Output of bar chart:
![image](https://github.com/user-attachments/assets/f7a931d1-4014-4d06-b2ff-cb9a154d825d)

## 3.Pie Chart
```
Shows proportions of categories
```
## code:
```
plt.figure(figsize=(6, 6))
plt.pie(df['Values'], labels=df['Category'], autopct='%1.1f%%', colors=['gold', 'skyblue', 'lightgreen', 'pink'])
plt.title('Pie Chart of Values by Category', fontsize=16)
plt.show()
```
## Output of Piechart:
![image](https://github.com/user-attachments/assets/ecac5f24-1ed9-4fa2-b7a9-39295c79d2a1)

## 4.Line Chart
```
Demonstrates trends over time
```
## code:
```
plt.figure(figsize=(8, 5))
plt.plot(df['Time'], df['Growth'], marker='o', color='blue', label='Growth Over Time')
plt.title('Line Chart of Growth Over Time', fontsize=16)
plt.xlabel('Year', fontsize=12)
plt.ylabel('Growth', fontsize=12)
plt.legend()
plt.grid()
plt.show()
```
## Line chart:
![image](https://github.com/user-attachments/assets/4afe2953-59fd-4fd5-8005-348a0bd6f0c0)

## Observations
## Data Cleaning
```
Missing values were replaced with calculated metrics or removed as required.
Improved data consistency.
```
## Basic Data Exploration
```
Mean Age: 28.0
Median Salary: 54000.0
Mode of Name: Alice
```
## Visualization Patterns
```
Bar Chart: Category C has the highest value.
Pie Chart: Category C holds the largest proportion.
Line Chart: Growth shows a steady rise, with a sharp increase from 2023 to 2024.
```
## Result
Data exploration and visualization were successfully performed using Python, resulting in a deeper understanding of data trends and patterns.
