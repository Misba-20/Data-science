# Weather Data Analysis and Visualization Using Pandas

## Project Overview

This project demonstrates how to perform **data cleaning, preprocessing, analysis, and visualization** on a weather dataset using **Pandas** and **Matplotlib**. The program reads weather data from a CSV file, identifies missing values, removes or replaces them using appropriate techniques, extracts useful information such as **year** and **month** from the date column, calculates yearly average temperatures, and visualizes the results with a line chart.

This project introduces fundamental data preprocessing techniques that are widely used in **Data Analytics**, **Machine Learning**, and **Data Science**.

---

## Objectives

- Read a weather dataset from a CSV file.
- Identify missing values in the dataset.
- Remove incomplete records when required.
- Replace missing temperature values using the mean.
- Convert string dates into datetime format.
- Extract year and month from the date.
- Perform yearly temperature analysis.
- Visualize average yearly temperatures using a line chart.

---

## Technologies Used

- Python 3.x
- Pandas
- Matplotlib

---

## Dataset

**Dataset Name:** `weather.csv`

### Dataset Description

The dataset contains weather-related information recorded over different dates. It includes average, minimum, and maximum temperature values along with the corresponding date.

### Dataset Columns

| Column Name | Description |
|-------------|-------------|
| time | Date of weather observation |
| tavg | Average Temperature |
| tmin | Minimum Temperature |
| tmax | Maximum Temperature |

---

## Project Workflow

### 1. Import Required Libraries

The project uses the following libraries:

```python
import pandas as pd
import matplotlib.pyplot as md
```

---

### 2. Read the Dataset

The weather dataset is loaded using Pandas.

```python
weather = pd.read_csv("weather.csv")
```

The original dataset is displayed.

---

### 3. Check Missing Values

The program checks for missing values using:

```python
weather.isnull().sum()
```

It also displays:

- Non-null values
- Rows containing missing values
- Complete records

Functions used:

- `isnull()`
- `notnull()`
- `dropna()`

---

### 4. Handle Missing Values

Missing values are handled using two different approaches.

### Removing Missing Values

```python
weather.dropna()
```

Other variations include:

- Remove columns with missing values
- Remove rows where all values are missing
- Remove rows containing any missing value

---

### Filling Missing Values

Instead of deleting important records, missing values in temperature columns are replaced with the **mean** of the respective column.

```python
weather['tavg'] = weather['tavg'].fillna(weather['tavg'].mean())
```

The same method is applied to:

- `tmin`
- `tmax`

This helps preserve the dataset while reducing data loss.

---

### 5. Convert Date Column

The **time** column is converted into datetime format.

```python
weather['time'] = pd.to_datetime(weather['time'], format="%d-%m-%Y")
```

This allows date-related operations to be performed efficiently.

---

### 6. Extract Year and Month

The program creates two new columns.

### Year

```python
weather['year'] = weather['time'].dt.year
```

### Month

```python
weather['month'] = weather['time'].dt.month
```

These columns simplify time-based analysis.

---

### 7. Group Data by Year

The program groups records based on year.

First, it counts the number of observations:

```python
weather.groupby("year")["tavg"].count()
```

Then, it calculates the average yearly temperature.

```python
weather.groupby("year")["tavg"].mean()
```

This provides the average temperature recorded for each year.

---

### 8. Visualize the Results

The project uses Matplotlib to create a **Line Chart**.

```python
md.plot(yearly["year"], yearly["tavg"])
```

The graph displays the variation in average temperature over different years.

---

## Features

- Reads weather data from a CSV file.
- Detects missing values.
- Removes incomplete records.
- Replaces missing values using the column mean.
- Converts date strings into datetime format.
- Extracts year and month.
- Performs yearly temperature analysis.
- Calculates average yearly temperatures.
- Displays a line graph for trend analysis.

---

## Sample Output

The program displays:

- Original Dataset
- Missing Value Summary
- Dataset after Removing Missing Values
- Dataset after Filling Missing Values
- Updated Dataset with Year and Month
- Year-wise Temperature Count
- Year-wise Average Temperature
- Line Graph showing Temperature Trend

---

## Visualization

### Chart Type

**Line Chart**

### X-Axis

Year

### Y-Axis

Average Temperature (`tavg`)

### Purpose

The graph illustrates how the average temperature changes over different years, making it easier to identify weather trends and climate variations.

---

## Learning Outcomes

After completing this project, you will understand how to:

- Read CSV files using Pandas.
- Detect missing values in datasets.
- Remove and replace missing values.
- Convert string data into datetime format.
- Extract date components such as year and month.
- Group data using `groupby()`.
- Calculate summary statistics.
- Visualize trends using Matplotlib.

---

## Applications

This project is useful in:

- Weather Data Analysis
- Climate Change Studies
- Environmental Monitoring
- Data Cleaning and Preprocessing
- Exploratory Data Analysis (EDA)
- Machine Learning Data Preparation
- Time Series Analysis

---

## Future Enhancements

The project can be extended by adding:

- Monthly temperature trend analysis
- Seasonal weather comparison
- Temperature forecasting using Machine Learning
- Correlation analysis between weather parameters
- Interactive visualizations using Plotly
- Dashboard creation using Streamlit or Power BI

---

## Conclusion

This project demonstrates the complete workflow of **data preprocessing and analysis** using a weather dataset. It covers essential techniques such as identifying and handling missing values, converting date formats, extracting meaningful time-based information, performing yearly aggregation, and visualizing temperature trends. These preprocessing and visualization methods are fundamental skills in **Data Science**, **Machine Learning**, and **Business Analytics**, making this project an excellent learning resource for beginners.

