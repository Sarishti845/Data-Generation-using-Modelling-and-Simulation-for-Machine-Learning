# 📊 Data Generation using Modelling and Simulation for Machine Learning

## 👩‍🎓 Student Details
**Name:** Sarishti  
**Course:** Modelling and Simulation for Machine Learning  
**Simulation Tool:** SimPy (Discrete Event Simulation Framework)

---

# 🎯 Objective

The objective of this project is to:

- Select a suitable computer simulation software.
- Identify important system parameters and determine their bounds.
- Generate synthetic data using simulation.
- Perform 1000 simulation runs.
- Apply multiple Machine Learning models.
- Compare model performance using evaluation metrics.
- Identify the best performing model.

This project demonstrates how simulation-generated data can be effectively used for Machine Learning tasks.

---

# 🖥 Simulation Tool / Method Used

## 🔹 SimPy (Open-Source)

SimPy is a Python-based discrete event simulation framework used to model queue-based and event-driven systems.

### Why SimPy?
- Open-source and lightweight
- Easy integration with Python ML libraries
- Suitable for modeling real-world queuing systems
- Efficient for synthetic dataset generation

---

# 🏦 Simulation Model: Bank Queue System

A single-server bank queue system was simulated:

- Customers arrive randomly (Poisson process).
- Service time follows an exponential distribution.
- Customers wait if the server is busy.
- Average waiting time is recorded.

Simulation runtime was fixed at **100 time units**.

---

# ⚙️ Parameters and Bounds (Step 3)

The following parameters were defined:

| Parameter       | Description                      | Lower Bound | Upper Bound |
|----------------|----------------------------------|------------|------------|
| arrival_rate   | Customer arrival rate (λ)        | 0.5        | 2.0        |
| service_rate   | Service rate (μ)                 | 1.0        | 3.0        |

These bounds ensure realistic queue behavior and system stability.

---

# 📤 Output Values Recorded

For each simulation run, the following output was recorded:

- **Average Waiting Time (avg_waiting_time)**

Since this is a continuous value, the problem is treated as a:

## 🔹 Regression Task

Target Variable:
avg_waiting_time
---

# 🗂 Dataset Generation (Step 4 + Step 5)

### Process Followed:

1. Random values generated for:
   - arrival_rate (0.5 to 2.0)
   - service_rate (1.0 to 3.0)
2. Parameters passed to simulation function.
3. Simulation executed for 100 time units.
4. Average waiting time calculated.
5. Process repeated **1000 times**.

### Dataset Details

- Total Simulations: **1000**
- Rows: 1000
- Columns: 3

| arrival_rate | service_rate | avg_waiting_time |

---

# 🤖 Machine Learning Task

## 🔹 Regression Problem

### Input Features:
- arrival_rate
- service_rate

### Target:
- avg_waiting_time

### Train-Test Split:
- 80% Training
- 20% Testing
- random_state = 42

---

# 🧠 ML Models Compared (Step 6)

The following regression models were implemented:

1. Linear Regression  
2. Decision Tree Regressor  
3. Random Forest Regressor  
4. Gradient Boosting Regressor  
5. K-Nearest Neighbors Regressor  
6. Support Vector Regressor (SVR)

---

# 📏 Evaluation Metrics Used

## 🔹 Mean Squared Error (MSE)
Measures average squared difference between predicted and actual values.

Lower MSE indicates better model performance.

## 🔹 R² Score (Coefficient of Determination)
Measures how well the model explains variance in the data.

Higher R² indicates better model performance.

---

# 📊 Model Performance Results

| Model              | MSE      | R² Score |
|--------------------|----------|----------|
| Linear Regression  | 15.263   | 0.482    |
| Decision Tree      | 7.490    | 0.746    |
| Random Forest      | 5.975    | 0.797    |
| Gradient Boosting  | 6.556    | 0.778    |
| KNN                | 5.918    | 0.799    |
| SVR                | 5.892    | **0.800** |

---

# 🥇 Best Model

## ✅ Support Vector Regressor (SVR)

- Lowest MSE
- Highest R² Score (0.800)
- Best overall predictive performance

---

# 📊 Visualizations

## 📊 Model Comparison (R² Score)

The following chart compares all regression models based on R² score:

<p align="center">
  <img src="model_comparison (1).png" width="800">
</p>

---

# 🔍 Key Insights

- Waiting time increases as arrival rate approaches service rate.
- System congestion strongly impacts waiting time.
- Non-linear models perform better than linear regression.
- Advanced ML models capture queue dynamics more effectively.

---

# 📁 Repository Structure
```

📂 Assignment Repository
├── Assignment.ipynb
├── README.md
├── model_comparison (1).png

```

---

# 🎓 Conclusion

This project successfully demonstrates:

- Application of discrete event simulation for synthetic data generation.
- Impact of system parameters on queue performance.
- Use of regression models to predict system behavior.
- Comparison of multiple ML models using statistical evaluation metrics.

The integration of Simulation and Machine Learning provides a powerful framework for analyzing and predicting real-world system performance.

---

# 🚀 Future Work

- Perform hyperparameter tuning.
- Apply cross-validation.
- Extend to multi-server system.
- Increase simulation runs beyond 1000.
- Deploy as an interactive dashboard.


