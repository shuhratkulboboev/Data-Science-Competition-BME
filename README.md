# Electricity Price Prediction

This project focuses on predicting the hour on the 5th day of a 5-day period when the price of electricity will exceed the balancing energy price. This prediction task is part of a competition where results are evaluated based on the AUC value of the ROC curve.

---

## Dataset Description

The dataset, `public_data.csv`, contains 5-day sequences extracted from a time series, with each row representing a quarter-hour. Descriptive and hierarchical data columns provide context for the time-series data.

### **Key Variables**
1. **Hierarchy Variables**:
   - `rowID`: Unique identifier for each row in the dataset.
   - `season`: Identifier for data season; increments over time.
   - `periodID`: Identifier for 5-day periods.
   - `day_in_period`: Indicates the day in a 5-day period (values: 0–4).
   - `hour` and `minute`: Time of day information.
   - `holiday`: Indicates if the day is a public holiday.
   - `weekday`: Day of the week.

2. **Descriptive Variables**:
   - Includes factors potentially influencing the target variable, though skewed for privacy.

3. **Target Variable**:
   - Predict whether the electricity price on `day_in_period == 4` exceeds the balancing energy price.

### **Files**
- **`public_data.csv`**: Main dataset for analysis and model development.
- **`sample_beadando_rand.csv`**: Example submission file showing required format.

---

## Objectives

1. **Data Understanding**:
   - Explore the dataset and understand variable relationships.
   - Visualize correlations and identify potential predictive features.

2. **Preprocessing**:
   - Handle missing values, outliers, and skewed data.
   - Normalize and engineer features as required.

3. **Model Development**:
   - Train models to predict the target variable for `day_in_period == 4`.
   - Compare model performance using AUC scores.

4. **Submission**:
   - Generate predictions in the required format.
   - Submit results to the leaderboard.

---

## Methodology

### **1. Data Preprocessing**
- Filter data for relevant rows (`day_in_period == 4` for prediction).
- Handle missing and skewed data in descriptive variables.
- Normalize features for consistent scaling.
- Split data into training and testing sets.

### **2. Feature Engineering**
- Create new features from time variables (e.g., time of day, weekend vs weekday).
- Engineer lag-based features to include historical data trends.

### **3. Modeling**
- Train models using historical data from the first 4 days to predict the target variable on the 5th day.
- Models used:
  - **Logistic Regression**
  - **Random Forest**
  - **Gradient Boosting Machines**
- Evaluate models using:
  - **AUC of the ROC curve**
  - Precision, Recall, and F1-Score

### **4. Submission**
- Ensure submission file matches `sample_beadando_rand.csv` format.
- Include all `rowID`s with predictions as probabilities (values between 0 and 1).

---

## Results

### **Evaluation Metrics**
- **AUC of ROC Curve**: Primary metric for competition evaluation.
- **Comparison of Models**:
  - Random Forest: AUC = 0.997
  - Gradient Boosting: AUC = 0.998 (best performing)



---


