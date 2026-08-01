# Regression

#  Price Prediction & Statistical Regression Modeling

An end-to-end regression analysis project demonstrating data cleaning, feature correlation analysis, outlier inspection, standardization, and multiple linear regression modeling.

This repository focuses on predicting **Used Car Prices (`CarPricesData.pkl`)** based on vehicle attributes (`Age`, `Kilometers Driven`, `Weight`, `Horsepower`, etc.) and generalizes regression workflows across real-world datasets including the **California Housing Dataset**.


##  Project Overview & Analytical Workflow

```text
[ Raw Data ] ──► [ EDA & Correlation ] ──► [ Outlier Detection ] ──► [ StandardScaler ] ──► [ Linear Regression ] ──► [ Evaluation ]

```

### 1. Exploratory Data Analysis (EDA)

* **Distribution & Correlation Analysis:** Leveraged Seaborn pair plots and correlation heatmaps to identify strong linear relationships between predictors and target variables (e.g., negative correlation between vehicle `Age` and `Price`).
* **Outlier & Range Inspection:** Analyzed numerical spreads (`describe()`) and box plots across features (`KM`, `Weight`, `CC`, `HP`).

### 2. Feature Scaling & Data Pipeline

* Applied `StandardScaler` to transform features onto a zero-mean and unit-variance scale:

$$\mathbf{x}_{\text{scaled}} = \frac{\mathbf{x} - \mu}{\sigma}$$


* Preserved spatial integrity and prevented data leakage between train/test partitions using $67/33$ train-test splits.

---

##  Model Performance & Evaluation

The primary model evaluates multiple feature combinations to predict used car market valuations:

| Model Setup | Predictors Used | Performance Metric ($R^2$ Score) | Mean Absolute Error (MAE) |
| --- | --- | --- | --- |
| **Simple Linear Regression** | `Age` | **`0.7611` (76.1%)** | `0.3343` (Scaled) |
| **Multiple Linear Regression** | `Age`, `KM`, `Weight`, `HP`, `CC`, `Doors`, `MetColor` | **`0.8599` (86.0%)** | `0.2702` (Scaled) |

> **Key takeaway:** Adding vehicle specifications like `Weight`, `Horsepower`, and mileage (`KM`) alongside vehicle `Age` boosted the model's explanatory power ($R^2$) by **~10%** while significantly reducing estimation error.

---

##  Visual Insights
<img width="1966" height="1966" alt="image" src="https://github.com/user-attachments/assets/334cc674-8562-4570-a011-8f5ee4ca0df3" />



##  Repository Structure

```text
├── CarPricesData.pkl              # Primary Used Car Dataset
├── car_price_regression.ipynb     # Jupyter Notebook containing full EDA & modeling
├── README.md                      # Documentation
└── requirements.txt               # Dependencies


##  Engineering Highlights

* **Proper Transformation Handling:** Demonstrates accurate usage of `fit_transform` vs. `transform` and `inverse_transform` to convert predictions back to original currency units.
* **Extensible Architecture:** Includes baseline experiments on standard benchmarks (California Housing dataset) to test feature scaling behavior across different dataset scales.

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for details.
