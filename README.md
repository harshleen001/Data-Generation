# Data-Generation
# Data Generation using Modelling and Simulation for Machine Learning

## Overview

This project demonstrates **data generation using simulation** and the subsequent **evaluation of machine learning models** using the generated synthetic data.

A **queueing system** was simulated using **SimPy**, a discrete-event simulation library in Python. The simulator was used to generate a dataset by varying system parameters and recording system performance. The generated data was then used to train and evaluate multiple machine learning models to identify the best-performing model.

---

## Objectives

- Select and explore a relevant simulation tool
- Identify important simulation parameters and their bounds
- Generate synthetic data using simulation
- Perform 1000 simulation runs
- Train and compare multiple machine learning models
- Report results using tables and graphs

---

## Simulation Tool Used

### SimPy

**SimPy** is a process-based discrete-event simulation framework in Python.  
It is widely used for modeling systems such as queues, networks, and resource-sharing environments.

**Why SimPy?**
- Lightweight and Python-native
- Ideal for queueing and process simulations
- Produces numerical outputs suitable for ML datasets

---

## Simulation Model Description

A **customer service queueing system** was simulated where:
- Customers arrive randomly
- They wait for service if servers are busy
- Waiting time is recorded as the output variable

---

## Simulation Parameters and Bounds

| Parameter       | Description                         | Lower Bound | Upper Bound |
|-----------------|-------------------------------------|-------------|-------------|
| Arrival Rate    | Average customer arrival rate       | 0.1         | 1.0         |
| Service Rate    | Average service time                | 0.5         | 5.0         |
| Servers         | Number of service counters          | 1           | 3           |
| Simulation Time | Total simulation duration (fixed)  | 50          | 50          |

These bounds ensure realistic and stable system behavior.

---

## Data Generation Process

1. Random values of parameters were generated within defined bounds
2. Each parameter set was passed to the SimPy simulation
3. Average waiting time was recorded
4. This process was repeated **1000 times**

---

## Generated Dataset

**Features:**
- `arrival_rate`
- `service_rate`
- `servers`

**Target Variable:**
- `avg_waiting_time`


The dataset was saved as:

simpy_simulation_data.csv


---

## Machine Learning Models Evaluated

Five regression models were trained and evaluated:

- Linear Regression
- Ridge Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor

---

## Evaluation Metrics

- **RMSE (Root Mean Squared Error)**
- **R² Score**

These metrics were used to compare predictive performance.

---

## Model Comparison Results

| Model               | RMSE  | R² Score |
|---------------------|-------|----------|
| Linear Regression   | ~3.63 | ~0.53    |
| Ridge Regression    | ~3.63 | ~0.53    |
| Decision Tree       | ~4.00 | ~0.43    |
| Random Forest       | ~3.46 | ~0.57    |
| Gradient Boosting   | ~3.11 | ~0.65    |

---

## Best Model Selection

**Gradient Boosting Regressor** achieved:
- Lowest RMSE
- Highest R² Score

➡️ **Selected as the best-performing model**

---

## Visualization

A bar graph was plotted to visually compare R² scores of all models, clearly showing the superior performance of Gradient Boosting.

---


