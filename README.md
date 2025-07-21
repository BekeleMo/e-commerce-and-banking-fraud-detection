---

## 📊 Datasets Used

### 1. Fraud_Data.csv
- E-commerce transaction logs with user, device, IP, and purchase info.
- Target: `class` (1 = Fraud, 0 = Legitimate)

### 2. creditcard.csv
- Credit card transaction logs with PCA-anonymized features.
- Target: `Class` (1 = Fraud, 0 = Legitimate)

### 3. IpAddress_to_Country.csv
- Maps IP ranges to countries for geolocation feature engineering.

---

## 📌 Interim Submission I: Data Preparation, EDA & Feature Engineering

This section covers all deliverables for the **Interim-1 submission**, focused on **Task 1**: Data Cleaning, EDA, and Feature Engineering.

---

### 🧼 Task 1.1: Data Cleaning and Preprocessing

- Removed duplicates from both datasets.
- Converted timestamps (`signup_time`, `purchase_time`) to datetime.
- Corrected data types (e.g., `ip_address` as string).
- Checked and handled missing values using:
  - Imputation (for `age` if missing).
  - Dropping if rows are non-critical and sparse.

---

### 📈 Task 1.2: Exploratory Data Analysis (EDA)

#### Univariate Insights:

- Purchase value is highly right-skewed.
- Majority of users are in the 20–40 age range.
- Majority class is **non-fraudulent** (high class imbalance).

#### Bivariate Insights:

- Fraud tends to occur more on certain browsers (e.g., Chrome).
- Some devices and IPs are associated with repeated fraud.
- Source of acquisition (Ads vs SEO) shows different fraud rates.

_Visuals included in `notebooks/eda_fraud.ipynb`._

---

### 🌍 Task 1.3: IP Address to Country Mapping

- Converted IP addresses to 32-bit integers using:

```python
import socket, struct
def ip_to_int(ip): return struct.unpack("!I", socket.inet_aton(ip))[0]
```
