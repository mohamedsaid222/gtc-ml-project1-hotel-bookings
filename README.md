# gtc-ml-project1-hotel-bookings
# 🏨 Hotel Bookings Analysis & Prediction

## 📌 Project Overview
This project analyzes the **Hotel Bookings dataset** and builds a machine learning model to predict whether a booking will be **canceled** or not.  
The workflow includes **EDA → Data Cleaning → Feature Engineering → Modeling → Evaluation**.

---
## 📂 Repository Structure
gtc-ml-project1-hotel-bookings/
│── hotel_bookings.csv # Dataset
│── hotel_bookings.ipynb # Notebook with analysis & modeling
│── README.md # Project documentation

----

---

## 🧪 Project Phases

### **Phase 1: Exploratory Data Analysis (EDA)**
- Generated dataset statistics (`.info()`, `.describe()`).
- Visualized **missing values** using heatmaps.
- Detected **outliers** in columns like `adr` and `lead_time`.
- Key issues identified:
  - Missing values in `company`, `agent`, `children`, `country`.
  - Extreme outliers in `adr`.
  - Potential duplicates.

📊 Example visualization:  
![Missing Data Heatmap](images/missing_data_heatmap.png)  

---

### **Phase 2: Data Cleaning**
- **Missing values handled**:
  - `company`, `agent` → filled with `0`.
  - `children` → filled with median.
  - `country` → filled with mode.
- **Duplicates removed**.
- **Outliers capped** (`adr > 1000` → set to `1000`).
- **Data types fixed** (dates formatted).
- **Leakage columns dropped**:
  - `reservation_status`
  - `reservation_status_date`

---

### **Phase 3: Feature Engineering & Preprocessing**
- Created new features:
  - `total_guests = adults + children + babies`
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`
  - `is_family` = 1 if children/babies > 0, else 0
- Encoding:
  - One-Hot Encoding for categorical variables (`meal`, `market_segment`, etc.).
  - Grouped rare countries into **"Other"**.
- Scaling applied to numerical features.
- Train/test split: **80/20**.

---

### **Phase 4: Modeling**
- Trained models:
  - **RandomForestClassifier** (baseline).
- Evaluation metrics:
  - **Accuracy** ~ 0.88 – 0.90
  - **Confusion Matrix**
  - **Classification Report**

📊 Example Confusion Matrix:  
![Confusion Matrix](images/confusion_matrix.png)  

---

## 📊 Results

| Metric        | Value |
|---------------|-------|
| Accuracy      | ~0.89 |
| Precision (0) | 0.89  |
| Recall (0)    | 0.93  |
| Precision (1) | 0.88  |
| Recall (1)    | 0.81  |

🔑 **Insights**:
- Longer lead times → higher cancellation chance.
- No deposit bookings → more likely to cancel.
- Families with children/babies → less likely to cancel.

---


   git clone https://github.com/your-username/gtc-ml-project1-hotel-bookings.git

