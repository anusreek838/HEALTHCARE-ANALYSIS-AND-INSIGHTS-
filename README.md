# HEALTHCARE-ANALYSIS-AND-INSIGHTS-
## 1 Problem Statement
- This project focuses on analyzing healthcare data to identify patient health patterns, medical histories, and healthcare costs. By combining medical examination records, hospitalization details, and customer profiles, the project aims to discover meaningful insights through data cleaning, transformation, analysis, and visualization. The findings help understand health trends, cost variations, and relationships between health indicators, supporting better healthcare decision-making
## 2.Data Description
The dataset consists of three tables containing healthcare-related information:
- Medical Examination: Includes BMI, HbA1C, heart issues, transplant history, cancer history, major surgeries, smoking status, and weight status.
- Hospitalization Details: Contains date of birth, healthcare charges, hospital tier, city tier, and state ID.
- Customer Profile: Includes customer ID and first name.
- These tables are combined using Customer ID to create a unified Healthcare dataset for analysis and visualization.
## 3.Data Pre-processing 
I) Data Cleaning
- Missing Values: Used COUNTIF() to count missing values marked with ?.=COUNTIF(range,"?")
- Missing Month: Replaced missing month values with September.Missing Year: Filled missing year using rounded average.=ROUND(AVERAGE(range),0)
- Mode Imputation: Filled missing Smoker, Hospital Tier, and City Tier values using MODE.SNGL() (or most frequent category).
- Missing State ID: Replaced missing values with Unknown.

II) Data Transformation
- Split Names: Used Text to Columns to separate Title, First Name, and Last Name.
- Major Surgeries: Converted text values into numerical values using SUBSTITUTE() and VALUE() where applicable.
- Consistency Check: Checked Heart Issues and Smoker columns for inconsistent values.
- Weight Status: Categorized BMI using IF().=IF(BMI<18.5,"Underweight",IF(BMI<25,"Normal Weight",IF(BMI<30,"Overweight","Obesity")))
- Diabetes Status: Categorized HbA1C using IF().=IF(HbA1C<5.7,"Normal",IF(HbA1C<6.5,"Prediabetes","Diabetes"))
- Date of Birth: Combined Year, Month, and Date using DATE().=DATE(Year,Month,Day)
- Age Calculation: Calculated age as of 8 June 2023 using DATEDIF().=DATEDIF(DOB,DATE(2023,6,8),"Y")
- Charges Formatting: Applied Currency format ($) to Charges column.
## 4. Exploratory Data analysis 
- Data Exploration, Analysis & Visualization
- Combined three tables into the Healthcare sheet using VLOOKUP and Customer ID.
- Created Pivot Tables to analyze cancer history, smoking, transplant history, major surgeries, and HbA1C.
- Analyzed healthcare charges by Weight Status, Diabetes Status, Hospital Tier, and State.
- Created Pie, Column, Bar, Scatter, and Line Charts.
- Built an interactive Dashboard with Weight Status and Diabetes Status slicers.
- Analyzed cancer history among smokers and non-smokers using Pie Charts.
- Compared total major surgeries and average HbA1C based on transplant history.
- Examined healthcare charges according to Weight Status and Diabetes Status.
- Compared average healthcare charges across hospital tiers and states.
- Explored the relationship between Age, BMI, and HbA1C using Scatter Plots.
- Analyzed the relationship between Age and healthcare charges using a Line Chart.
- Created an interactive dashboard with slicers for Weight Status and Diabetes Status to visualize key insights
