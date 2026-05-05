# Water Potability Prediction and Scenario Analysis  
### Advanced Modeling and Optimization  
### Student ID: JOSZIM1500  
### Date: May 2026

---

## 📌 Project Overview

This project analyzes the **Water Potability Dataset** to determine whether water samples are safe for human consumption based on physicochemical properties.  
The work is divided into multiple analytical tasks:

1. **Data Preparation & Feature Scaling**  
2. **Model Optimization (Classification, Regression, Clustering)**  
3. **Scenario Analysis (Week 5)**  
4. **Sensitivity Analysis**  
5. **Portfolio Deployment via GitHub**

The primary classification model used for scenario analysis is the **optimized Logistic Regression model** developed in Week 4.

---

## 📊 Dataset Description

The dataset includes the following features:

- **pH**  
- **Hardness**  
- **Solids**  
- **Chloramines**  
- **Sulfate**  
- **Conductivity**  
- **Organic Carbon**  
- **Trihalomethanes**  
- **Turbidity**  
- **Potability** (Target: 0 = Not Potable, 1 = Potable)

Missing values were handled using **mean imputation**.

---

## 🤖 Optimized Models (Week 4)

### **1. Classification Model — Logistic Regression**
- Tuned using GridSearchCV  
- Best hyperparameters selected  
- Accuracy achieved: ~0.63  
- Used for **scenario analysis** and **sensitivity analysis**

### **2. Regression Model — Ridge Regression**
- Predicts Hardness  
- Tuned using GridSearchCV  
- Very low MSE achieved

### **3. Clustering Model — KMeans**
- Optimal clusters: **k = 2**  
- Evaluated using Silhouette Score

---

## 🧪 Scenario Analysis (Week 5)

Three realistic environmental and operational scenarios were created to test model robustness:

### **Scenario 1 — Industrial Contamination**
- Solids ↑ 30%  
- Sulfate ↑ 20%  
- Trihalomethanes ↑ 15%  
**Purpose:** Simulates industrial runoff increasing mineralization and disinfection byproducts.

### **Scenario 2 — Disinfection Failure**
- Chloramines ↓ 30%  
- Turbidity ↑ 40%  
**Purpose:** Represents a treatment plant malfunction leading to microbial risk.

### **Scenario 3 — Drought Mineralization**
- Hardness ↑ 25%  
- Solids ↑ 25%  
- Conductivity ↑ 25%  
- pH ↑ 0.3  
**Purpose:** Models drought conditions concentrating minerals.

Each scenario was scaled using the **same StandardScaler** used during model training.

---

## 📈 Scenario Impact Summary

For each scenario, the following metrics were computed:

- **Mean predicted potability probability**  
- **Share of samples predicted potable (p > 0.5)**  
- **Comparison to baseline predictions**

This analysis reveals how environmental changes influence water safety predictions.

---

## 🔍 Sensitivity Analysis

A two‑feature sensitivity analysis was performed on:

- **Chloramines**  
- **Turbidity**

These features were varied across their 10th–90th percentiles while holding all other features constant.

### Key Findings:
- Higher **Chloramines** → Higher potability probability  
- Higher **Turbidity** → Lower potability probability  
- Worst‑case combination: **Low Chloramines + High Turbidity**  
- Model behavior aligns with real‑world water safety expectations

A heatmap visualization was generated to illustrate the interaction effect.

---

## 🛠️ Dependencies

This project uses the following Python libraries:

- pandas  
- numpy  
- scikit‑learn  
- seaborn  
- matplotlib  
- jupyter  
