## 📊 Datasets Used

### 1. Fraud_Data.csv
- **Description**: Contains e-commerce transaction logs with fields such as `user_id`, `device_id`, `ip_address`, `purchase_time`, `purchase_value`, `signup_time`, `source`, `browser`, and `age`. Designed to identify fraudulent activities based on user behavior and transaction patterns.
- **Target Variable**: `class` (1 = Fraudulent, 0 = Legitimate).
- **Size**: [Add approximate rows/columns if known, e.g., 1M rows, 10 columns].
- **Source**: [Specify if applicable, e.g., synthetic data or public dataset].

### 2. creditcard.csv
- **Description**: Includes credit card transaction logs with PCA-anonymized features (e.g., `V1`, `V2`, ..., `V28`) for privacy, along with `Time`, `Amount`, and `Class`. Suitable for machine learning-based fraud detection.
- **Target Variable**: `Class` (1 = Fraudulent, 0 = Legitimate).
- **Size**: [e.g., 284,807 rows, 31 columns].
- **Source**: [e.g., Kaggle or internal data].

### 3. IpAddress_to_Country.csv
- **Description**: A lookup table mapping IP address ranges to countries, enabling geolocation-based feature engineering with columns like `lower_bound_ip`, `upper_bound_ip`, and `country`.
- **Size**: [e.g., 100,000+ rows].
- **Source**: [e.g., public IP geolocation database].

---

## 📌 Interim Submission I: Data Preparation, EDA & Feature Engineering

This section details the deliverables for the **Interim-1 submission**, focusing on **Task 1**: Data Cleaning, Exploratory Data Analysis (EDA), and Feature Engineering. The objective is to prepare high-quality data and derive actionable insights for detecting fraudulent transactions in e-commerce and banking systems.

---

### 🧼 Task 1.1: Data Cleaning and Preprocessing

- **Duplicate Removal**: Eliminated duplicate entries from both datasets using data deduplication techniques to ensure data integrity.
- **Timestamp Conversion**: Transformed `signup_time` and `purchase_time` into datetime objects for temporal analysis with:
  ```python
  import pandas as pd
  df['signup_time'] = pd.to_datetime(df['signup_time'])
  df['purchase_time'] = pd.to_datetime(df['purchase_time'])