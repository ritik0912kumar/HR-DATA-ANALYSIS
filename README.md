# HR-DATA-ANALYSIS

## HR Data Analysis of Employee Attrition at Fussion Innovista

#### Introduction

Employee attrition is a critical concern for companies as it directly impacts productivity, morale, and the financial health of the organization. Fussion Innovista is undertaking a comprehensive HR data analysis to understand the factors contributing to employee attrition. This analysis focuses on various parameters such as age, salary, tenure, department, and performance ratings. The goal is to identify patterns and trends that can help in formulating effective retention strategies.

#### Data Collection

The dataset comprises employee records from the past five years, including:
- Employee ID
- Age
- Gender
- Department
- Job Role
- Tenure
- Salary
- Performance Rating
- Attrition Status (Yes/No)

#### Data Cleaning Using Python

Before diving into the analysis, it is essential to clean the data to ensure accuracy and reliability. Data cleaning involves handling missing values, correcting inconsistencies, and removing duplicate records. Here is a summary of the data cleaning steps performed using Python:

1. **Importing Libraries**:
   ```python
   import pandas as pd
   import numpy as np
   ```

2. **Loading the Dataset**:
   ```python
   data = pd.read_csv('employee_data.csv')
   ```

3. **Handling Missing Values**:
   - Checking for missing values:
     ```python
     data.isnull().sum()
     ```
   - Filling or dropping missing values:
     ```python
     data['Age'].fillna(data['Age'].median(), inplace=True)
     data.dropna(subset=['Salary'], inplace=True)
     ```

4. **Correcting Inconsistencies**:
   - Standardizing categorical values:
     ```python
     data['Department'] = data['Department'].str.lower()
     ```

5. **Removing Duplicates**:
   ```python
   data.drop_duplicates(inplace=True)
   ```
### Snapsort of Cleaned Data
![Screenshot 2024-07-04 103159](https://github.com/ritik0912kumar/HR-DATA-ANALYSIS/assets/126445623/e93403ec-cc3a-4636-ba81-3b37652eb592)


#### Data Analysis

The cleaned dataset is now ready for analysis. The focus is on understanding how different factors influence employee attrition. Key analyses include:

1. **Attrition Rate by Age**:
   - Grouping data by age brackets to see which age group has the highest attrition rate.
   - Example analysis:
     ```python
     age_group = pd.cut(data['Age'], bins=[20, 30, 40, 50, 60], labels=['20-30', '30-40', '40-50', '50-60'])
     age_attrition = data.groupby(age_group)['Attrition'].mean()
     ```

2. **Salary and Attrition**:
   - Examining the correlation between salary levels and attrition.
   - Example analysis:
     ```python
     salary_attrition = data.groupby('Salary')['Attrition'].mean()
     ```

3. **Departmental Analysis**:
   - Identifying which departments have higher attrition rates.
   - Example analysis:
     ```python
     department_attrition = data.groupby('Department')['Attrition'].mean()
     ```

#### Dashboard Creation

To visualize the insights derived from the analysis, dashboards are created using Power BI and Excel. These dashboards provide an interactive and comprehensive view of the attrition analysis.

1. **Power BI Dashboard**:
   - **Age Analysis**: A bar chart showing attrition rates across different age groups.
   - **Salary Analysis**: A scatter plot to visualize the relationship between salary and attrition.
   - **Departmental Analysis**: A heatmap highlighting departments with high attrition rates.
   - **Interactive Filters**: Filters for job roles, performance ratings, and tenure to drill down into specific segments.

### Snapsort of Final Dashboard
![Screenshot 2024-07-04 103046](https://github.com/ritik0912kumar/HR-DATA-ANALYSIS/assets/126445623/a3543acd-10f9-468f-98b7-5a2374cb68f3)

![Screenshot 2024-07-04 103109](https://github.com/ritik0912kumar/HR-DATA-ANALYSIS/assets/126445623/448256ab-ebb4-4603-a909-0676247702c1)


2. **Excel Dashboard**:
   - **Pivot Tables**: To summarize attrition data by age, salary, and department.
   - **Charts and Graphs**: Line charts for trend analysis and pie charts for proportional representation.
   - **Slicers**: For interactive filtering and detailed analysis.

#### Conclusion

By conducting a thorough HR data analysis and creating interactive dashboards, Fussion Innovista aims to gain valuable insights into the factors driving employee attrition. This data-driven approach will aid in developing targeted strategies to improve employee retention, thereby enhancing overall organizational performance. The use of Python for data cleaning ensures the accuracy of the analysis, while Power BI and Excel dashboards provide an effective medium for communicating these insights to stakeholders of Fussion Innovista.
