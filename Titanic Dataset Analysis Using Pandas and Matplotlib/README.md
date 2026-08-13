# Titanic Dataset Analysis Using Pandas and Matplotlib

## Project Overview

This project demonstrates the use of **Pandas** and **Matplotlib** for performing basic data analysis and visualization on the **Titanic Dataset**. The program reads the dataset from a CSV file, performs data exploration, renames columns for better readability, filters passenger records based on survival status, computes survival statistics, and visualizes the results using a bar chart.

The project is designed for beginners who are learning **Python for Data Science** and covers essential data manipulation techniques using the Pandas library.

---

## Objectives

- Read a CSV dataset using Pandas.
- Rename dataset columns for better understanding.
- Explore the dataset structure.
- Filter survivor and non-survivor records.
- Calculate the number of survivors and non-survivors.
- Compute survival percentages.
- Visualize survival statistics using a bar chart.

---

## Technologies Used

- Python 3.x
- Pandas
- Matplotlib

---

## Dataset

**Dataset Name:** `gender_submission.csv`

### Dataset Description

The dataset contains information about Titanic passengers and whether they survived or not.

### Columns

| Column Name | Description |
|-------------|-------------|
| PassengerId | Unique Passenger ID |
| Survived | Survival Status (0 = Not Survived, 1 = Survived) |

---

## Project Workflow

### 1. Import Required Libraries

The project imports the following libraries:

- Pandas
- Matplotlib

```python
import pandas as pd
import matplotlib.pyplot as mp
```

---

### 2. Read the Dataset

The dataset is loaded using the `read_csv()` function.

```python
titanic = pd.read_csv("gender_submission.csv")
```

---

### 3. Rename Columns

The program demonstrates two methods of renaming columns.

#### Method 1: Using `inplace=True`

```python
titanic.rename(columns={
    "PassengerId":"ID",
    "Survived":"Status for clarity"
}, inplace=True)
```

#### Method 2: Creating a New DataFrame

```python
new = titanic.rename(columns={
    "PassengerId":"ID",
    "Survived":"Status for clarity"
})
```

---

### 4. Explore the Dataset

The following functions are used:

- `head(10)` → Displays first 10 records
- `tail(10)` → Displays last 10 records
- `info()` → Displays dataset information
- `shape` → Displays number of rows and columns

---

### 5. Filter the Data

The program filters:

- First 10 Survivors
- First 10 Non-Survivors

Example:

```python
titanic[titanic["Status for clarity"]==1]
```

---

### 6. Count Survivors

The program calculates:

- Total Survivors
- Total Non-Survivors

using

```python
value_counts()
```

Example:

```python
count = titanic["Status for clarity"].value_counts()
```

---

### 7. Calculate Survival Percentage

The percentage is calculated using

```
Percentage = (Number of Survivors / Total Passengers)
```

Similarly, the percentage of non-survivors is also calculated.

---

### 8. Visualize the Results

A **Bar Chart** is created using Matplotlib.

```python
count.plot(kind='bar')
```

The chart displays

- Survivors
- Non-Survivors

---

## Features

- Read CSV data using Pandas.
- Rename columns for better readability.
- Display dataset information.
- Filter records based on conditions.
- Count occurrences using `value_counts()`.
- Calculate percentages.
- Create bar chart visualization.
- Beginner-friendly implementation.

---

## Sample Output

The program displays:

- Original Dataset
- Renamed Dataset
- First 10 Records
- Last 10 Records
- Dataset Information
- Dataset Shape
- Top 10 Survivors
- Top 10 Non-Survivors
- Total Survivor Count
- Total Non-Survivor Count
- Survivor Percentage
- Non-Survivor Percentage

Finally, a bar chart comparing survivors and non-survivors is displayed.

---

## Visualization

### Chart Type

**Bar Chart**

### X-Axis

Survival Status

- 0 → Not Survived
- 1 → Survived

### Y-Axis

Number of Passengers

### Title

```
Survived vs Non Survived
```

---

## Learning Outcomes

After completing this project, you will understand:

- Reading datasets using Pandas.
- Renaming DataFrame columns.
- Exploring datasets.
- Filtering records using conditions.
- Counting categorical values.
- Calculating percentages.
- Creating visualizations with Matplotlib.
- Basic data analysis workflow in Python.

---

## Applications

This project can be used in:

- Data Analytics
- Data Science
- Machine Learning Preprocessing
- Exploratory Data Analysis (EDA)
- Python Programming Practice
- Educational Lab Experiments

---

## Future Enhancements

Some additional analyses that can be added include:

- Pie Chart of Survival Distribution
- Gender-wise Survival Analysis
- Age-wise Survival Analysis
- Passenger Class Analysis
- Correlation Heatmap
- Interactive Charts using Plotly
- Dashboard using Streamlit

---

## Conclusion

This project provides a simple and practical introduction to **Exploratory Data Analysis (EDA)** using the Titanic dataset. By utilizing **Pandas** for data manipulation and **Matplotlib** for visualization, the program demonstrates essential data analysis techniques such as reading datasets, renaming columns, filtering records, computing statistics, and presenting insights through charts. It serves as an excellent beginner-level project for understanding the fundamentals of data preprocessing and visualization in Python.
