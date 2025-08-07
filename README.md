# assignment-5-Ai

**Hypothetical AI Problem:**
*“Forecasting National Carbon Emissions to Support Climate Action (SDG 13)”*

**Objectives:**

1. Predict CO₂ emissions for each country using historical data.
2. Identify countries with rising emission trends to guide policy intervention.
3. Enable near real-time emissions tracking for global climate agreements.

**Stakeholders:**

* Government environmental agencies (e.g., Kenya’s NEMA).
* International organizations (e.g., UNFCCC, IPCC).

**Key Performance Indicator (KPI):**

* **Root Mean Square Error (RMSE)** between predicted and actual CO₂ emissions.

---

### **2. Data Collection & Preprocessing (8 points)**

**Two Data Sources:**

1. **World Bank – Our World in Data (OWID)**: Global CO₂ emissions by country and year.
2. **UNFCCC Public Dataset**: Verified emissions and policy reports.

**One Potential Bias in the Data:**

* **Underreporting Bias**: Some developing countries may have incomplete or outdated emissions records due to lack of advanced monitoring infrastructure.

**Three Preprocessing Steps:**

1. **Handling Missing Data**: Impute using interpolation or country-level averages.
2. **Feature Engineering**: Create new features such as “emissions per capita” and “GDP-emission ratio.”
3. **Normalization**: Scale numeric features using Min-Max normalization for better model performance.

---

### **3. Model Development (8 points)**

**Model Choice:**

* **Random Forest Regressor**
  Justification: Robust to overfitting, interpretable, and handles non-linear relationships well. Ideal for tabular time-series data like emissions.

**Data Splitting Strategy:**

* **70% Training**, **15% Validation**, **15% Testing**
  Use time-based splitting to preserve temporal integrity (e.g., training on 2000–2018, testing on 2019–2023).

**Two Hyperparameters to Tune:**

1. **n\_estimators**: Number of trees in the forest. Affects accuracy and performance.
2. **max\_depth**: Controls how deep each tree grows, influencing bias-variance trade-off.

---

### **4. Evaluation & Deployment (8 points)**

**Two Evaluation Metrics:**

1. **Mean Absolute Error (MAE)** – Intuitive and less sensitive to outliers.
2. **R² Score** – Measures proportion of variance explained by the model.

**What is Concept Drift?**

* It refers to the change in the relationship between features and target variable over time.
* *Example*: New climate regulations may suddenly reduce emissions.

**Monitoring Concept Drift:**

* Use performance monitoring dashboards, retrain models periodically, or apply drift detection methods like DDM or ADWIN.

**One Technical Deployment Challenge:**

* **Scalability**: Emission forecasting tools may require deployment across global servers.
  *Solution:* Use cloud platforms (e.g., AWS SageMaker) and deploy using containers (e.g., Docker) for scalability and flexibility.

