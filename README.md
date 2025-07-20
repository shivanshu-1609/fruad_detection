# 💳 Fraud Transaction Detection Using Machine Learning

This project focuses on detecting fraudulent credit card transactions using a real-world transaction dataset. The goal is to build a robust model that can identify suspicious (fraudulent) transactions with high precision and recall.

---

## 📁 Dataset Overview

The dataset consists of 183 `.pkl` files representing transaction data over different days. Each file contains features like:

- `TRANSACTION_ID`, `CUSTOMER_ID`, `TERMINAL_ID`
- `TX_AMOUNT`, `TX_TIME_SECONDS`, `TX_DATETIME`, `TX_FRAUD`
- Temporal and aggregated behavioral features

---

## 🧪 Project Pipeline

### 1. 🧼 Data Loading & Preprocessing
- Combined all `.pkl` files into one DataFrame.
- Handled missing values and removed unnecessary columns.
- Converted timestamps and extracted:
  - `HOUR`, `DAY_OF_WEEK`, `TX_DATE`

### 2. 📊 Exploratory Data Analysis (EDA)
- Fraud vs Legit transaction count and ratio
- Amount distribution for fraud and legit
- Temporal patterns of fraud (hour, day of week)

### 3. ⚖️ Data Balancing
- Downsampled legitimate transactions to handle class imbalance
- Used a 1:5 ratio of fraud:legit transactions in training

### 4. 📏 Feature Scaling
- Scaled numerical features using `StandardScaler`:
  - `TX_AMOUNT`, `TX_TIME_SECONDS`, `AMOUNT_OVER_AVG`, etc.

### 5. 🏗 Feature Engineering
- Created behavioral features like:
  - `CUSTOMER_TX_COUNT_1DAY`, `CUSTOMER_TX_AMOUNT_1DAY`
  - `TERMINAL_TX_COUNT_1DAY`, `TERMINAL_FRAUD_COUNT_1DAY`
  - `CUSTOMER_AVG_AMOUNT_1DAY`, `AMOUNT_OVER_AVG`

### 6. 🤖 Model Building
- Used **Random Forest Classifier**
- Trained on balanced dataset
- Evaluated on real-world distribution

### 7. 📈 Model Evaluation
- **Confusion Matrix**  
- **Classification Report**  
  - Accuracy: **~100%**
  - Precision (fraud class): **0.74**
  - Recall (fraud class): **1.00**
  - ROC AUC Score: **0.9999**

---

## 🧠 Final Result

The model performed extremely well on unseen test data. Most fraudulent transactions were correctly identified with very few false negatives.

---

## 💾 Saved Artifacts

- Trained Model: `fraud_detection_model.pkl`
- Can be loaded using `joblib.load()`

---

## 🚀 Future Improvements

- Try ensemble methods (XGBoost, LightGBM)
- Use time-based cross-validation
- Add real-time streaming inference (using Kafka / Spark)
- Deploy using Flask or FastAPI

---

## 👨‍💻 Author

**Shivanshu Shukla**  
Electronics & AI Enthusiast | GATE 2026 Aspirant | ML & Data Science Practitioner

---

## 📝 License

This project is for educational and research purposes.