# TLC-Driver-Analysis

This project provides an interactive dashboard built with Dash and Plotly to analyze TLC Driver Application data. It enables users to explore application statuses, visualize trends over time, and identify common rejection reasons through a user-friendly interface.

## Key Features ##

1. Data Loading and Preprocessing:
- Loads data from `TLC_New_Driver_Application.csv`.
- Handles missing values with median imputation for numerical columns and most frequent value imputation for categorical columns.
- Removes outliers using the interquartile range (IQR) method.
- Scales numerical features with `StandardScaler`.
- Encodes categorical variables using `LabelEncoder` for binary categories and `OneHotEncoder` for multi-category variables (excluding text fields like 'Other Requirements').

2. Feature Engineering:
- Extracts date-related features from 'App Date' (year, quarter, month, day, day of week, weekend indicator).
- Creates an approval flag and calculates monthly approval rates.
- Optionally applies PCA and feature selection (`SelectKBest`) if there are more than 10 numerical features.

3. Interactive Dashboard:
- **Filters:** Select date range and application statuses.
- **Overview Tab:** Bar chart displaying the distribution of application statuses.
- **Visuals Tab:** Stacked bar chart showing applications by month and status.
- **Insights Tab:** Displays the acceptance rate and top rejection reasons.
- **Cards:** Shows key metrics (total applications, approved, denied, and acceptance rate).

4. Insights:
- Calculates the percentage of accepted applications.
- Identifies and lists the most common rejection reasons.

5. Notes
- The dashboard uses a dark theme (DARKLY) for improved visibility.
- Includes error handling for empty data after filtering and invalid date formats.
- Optional PCA and feature selection are included in feature engineering, which may not be necessary for all datasets.
- The code is modular, with separate functions for data loading, preprocessing, feature engineering, and dashboard rendering.
