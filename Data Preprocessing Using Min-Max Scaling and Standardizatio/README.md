# Shopping Dataset Feature Scaling Using Scikit-learn

## Project Overview

This project demonstrates the process of **data preprocessing** by applying **Feature Scaling** techniques to a shopping dataset using **Scikit-learn**. Feature scaling is an important step in machine learning as it ensures that numerical features are on a comparable scale, improving the performance and convergence of many machine learning algorithms.

The project applies two popular scaling techniques:

- **Min-Max Scaling (Normalization)**
- **Standard Scaling (Standardization)**

Additionally, it visualizes the distribution of the **Avg_Price** feature using a histogram.

---

## Objectives

- Read the shopping dataset using Pandas.
- Identify all numerical columns automatically.
- Apply Min-Max Scaling to normalize numerical features.
- Apply Standard Scaling to standardize numerical features.
- Display the transformed datasets.
- Visualize the distribution of average prices using a histogram.

---

## Technologies Used

- Python 3.x
- Pandas
- Matplotlib
- Scikit-learn

---

## Dataset

**Dataset Name:** `shopping.csv`

### Dataset Description

The shopping dataset contains information related to products and their numerical attributes such as average price, quantity, sales, or other measurable values. The program automatically detects all numeric columns and performs scaling operations on them.

---

## Project Workflow

### 1. Import Required Libraries

The following libraries are imported:

```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.preprocessing import MinMaxScaler
from sklearn.preprocessing import StandardScaler
```

---

### 2. Read the Dataset

The dataset is loaded using Pandas.

```python
shopping = pd.read_csv("shopping.csv")
```

The original dataset is displayed.

---

### 3. Select Numerical Columns

The program automatically identifies all numerical columns.

```python
numeric_col = shopping.select_dtypes(include='number').columns
```

This ensures that only numeric features are selected for scaling.

---

### 4. Apply Min-Max Scaling

The program normalizes the numerical data using **MinMaxScaler**.

```python
scaler = MinMaxScaler()
shopping_normalized = scaler.fit_transform(shopping[numeric_col])
```

### Formula

\[
X_{new} = \frac{X - X_{min}}{X_{max} - X_{min}}
\]

### Characteristics

- Values are scaled between **0 and 1**.
- Preserves the original distribution.
- Commonly used in Neural Networks and Distance-Based Algorithms.

---

### 5. Apply Standard Scaling

The program standardizes the numerical data using **StandardScaler**.

```python
scaler = StandardScaler()
shopping_standardized = scaler.fit_transform(shopping[numeric_col])
```

### Formula

\[
Z = \frac{X-\mu}{\sigma}
\]

Where

- **μ** = Mean
- **σ** = Standard Deviation

### Characteristics

- Mean becomes **0**.
- Standard deviation becomes **1**.
- Useful for Logistic Regression, SVM, PCA, and K-Means.

---

### 6. Display Transformed Data

The first five rows of both datasets are displayed.

- Normalized Dataset
- Standardized Dataset

This allows comparison between both scaling techniques.

---

### 7. Visualize Data Distribution

The project creates a histogram of the **Avg_Price** column.

```python
plt.hist(shopping['Avg_Price'], bins=10)
```

The histogram shows how product prices are distributed across different price ranges.

---

## Features

- Reads CSV data using Pandas.
- Automatically detects numerical columns.
- Performs Min-Max Normalization.
- Performs Standardization using Z-score.
- Displays transformed datasets.
- Creates histogram visualization.
- Suitable for machine learning preprocessing.

---

## Sample Output

The program displays:

- Original Shopping Dataset
- Numerical Columns
- Normalized Dataset (First 5 Records)
- Standardized Dataset (First 5 Records)
- Histogram of Average Price

---

## Visualization

### Chart Type

**Histogram**

### X-Axis

Average Price (`Avg_Price`)

### Y-Axis

Frequency

### Title

```
Histogram
```

---

## Advantages of Feature Scaling

### Min-Max Scaling

- Converts values into a fixed range (0–1).
- Maintains relationships among data.
- Useful for algorithms based on distance calculations.

### Standard Scaling

- Centers the data around zero.
- Handles features with different units.
- Preferred for many machine learning algorithms.

---

## Learning Outcomes

After completing this project, you will understand how to:

- Read datasets using Pandas.
- Identify numerical features automatically.
- Normalize data using MinMaxScaler.
- Standardize data using StandardScaler.
- Compare different scaling techniques.
- Visualize feature distributions using Matplotlib.
- Prepare datasets for machine learning applications.

---

## Applications

This project is useful in:

- Machine Learning
- Data Science
- Predictive Analytics
- Customer Purchase Analysis
- Retail Analytics
- Data Preprocessing
- Feature Engineering
- Statistical Analysis

---

## Future Enhancements

The project can be extended by adding:

- Box Plot for Outlier Detection
- Scatter Plot Analysis
- Correlation Heatmap
- Feature Selection Techniques
- Principal Component Analysis (PCA)
- K-Means Clustering
- Machine Learning Model Training
- Interactive Dashboard using Streamlit

---

## Conclusion

Feature scaling is an essential preprocessing step in machine learning because it ensures that numerical features contribute equally during model training. In this project, the shopping dataset is successfully preprocessed using **Min-Max Scaling** and **Standard Scaling**, allowing numerical features to be transformed into comparable scales. The histogram provides additional insight into the distribution of the **Avg_Price** feature. This project serves as a strong foundation for understanding data preprocessing techniques before building machine learning models.

