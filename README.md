# Payroll Anomaly Detection System (AI/ML)

## Overview
This project implements an **AI-powered payroll anomaly detection system** designed to identify **salary manipulation** and **fake overtime claims** using **unsupervised machine learning**.  
The solution is built to resemble **real-world enterprise payroll systems**, supporting **batch processing**, **real-time detection**, and **concept drift handling**.

The system uses **Isolation Forest** to learn normal payroll behavior and flag rare, abnormal patterns without requiring labeled fraud data.

---

## Problem Statement
Payroll systems often suffer from:
- Salary manipulation
- Fake or inflated overtime claims
- Changing payroll policies over time

Challenges include:
- Lack of labeled fraud data
- Need for real-time alerts
- Continuous changes in salary and work patterns (concept drift)

This project addresses these challenges using an **unsupervised anomaly detection approach**.

---

## Key Features
- Unsupervised anomaly detection (no labels required)
- Detection of:
  - Salary manipulation
  - Fake overtime claims
- Batch pipeline for audits and retraining
- Real-time pipeline for instant anomaly detection
- Concept drift detection and handling
- Department-wise anomaly analysis
- Industry-standard deployment design

---

## System Architecture
The system follows a **dual-pipeline architecture**:

- **Batch Pipeline**
  - Processes historical payroll data
  - Generates audit reports
  - Detects concept drift
  - Retrains the model when required

- **Real-Time Pipeline**
  - Scores payroll events instantly
  - Flags suspicious transactions
  - Sends alerts for manual review

Architecture details are documented in: DEPLOYMENT_PLAN.md


---

## Machine Learning Approach

### Algorithm Used
**Isolation Forest**

**Why Isolation Forest?**
- Works without labeled data
- Handles high-dimensional payroll features
- Assumes anomalies are rare (true for fraud)
- Efficient and scalable for real-time systems

---

## Feature Engineering
Key features used by the model:
- `base_salary`
- `overtime_hours`
- `overtime_pay`
- `overtime_pay_per_hour`
- `salary_deviation` (from department average)
- `department_encoded`

These features capture abnormal payroll behavior effectively.

---

## Concept Drift Handling
Concept drift occurs when normal payroll behavior changes over time due to:
- Salary hikes
- Policy changes
- Seasonal workload changes

### How Drift Is Handled:
- Monitor feature distributions
- Track anomaly rate trends
- Compare historical vs recent data
- Retrain model using recent batch data when drift is detected

Drift handling is performed **only in the batch pipeline**, ensuring stability in real-time operations.

---

## Data
- Synthetic payroll dataset created to simulate real-world scenarios
- No sensitive or real employee data is used

Dataset file:
payroll_data.csv


---

## Project Structure
payroll-anomaly-detection/
├── anomaly_detection_engine.ipynb
├── payroll_anomaly_dataset.csv
├── deployment_plan.md
├── README.md


---

## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook
- Git & GitHub

---

## How to Run the Project
1. Clone the repository
2. Open `anomaly_detection_engine.ipynb`
3. Run the notebook cells sequentially
4. View anomaly detection results and visualizations

---

## Future Improvements
- Integration with live payroll systems
- Advanced drift detection techniques (PSI, KL-divergence)
- Alert dashboards for HR and finance teams
- Model explainability for anomaly reasons

---

## Conclusion
This project demonstrates how **unsupervised machine learning** can be effectively applied to **real-world payroll anomaly detection**, with a strong emphasis on **scalability**, **robustness**, and **industry best practices**.

---

## Author
**Riyanshi Verma**  
AI/ML Enthusiast | Payroll Anomaly Detection Project
