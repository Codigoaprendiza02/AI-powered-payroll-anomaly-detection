### Pesudocode of the complete system
```
BEGIN

LOAD latest_model, scaler, encoders

--------------------------------
BATCH PIPELINE (Scheduled)
--------------------------------
FETCH historical_payroll_data

PREPROCESS data
ENGINEER features
ENCODE categorical features
SCALE numerical features

SCORE anomalies using model
STORE anomaly results

CHECK concept_drift:
    COMPARE old vs new feature distributions
    MONITOR anomaly rate

IF drift_detected:
    RETRAIN model on recent data
    VALIDATE new model
    DEPLOY new_model as latest version

--------------------------------
REAL-TIME PIPELINE (Event-Based)
--------------------------------
ON new_payroll_event:
    ADD current datetime
    PREPROCESS event
    ENGINEER required features
    ENCODE & SCALE using deployed scaler
    PREDICT anomaly score

    IF anomaly_score exceeds threshold:
        FLAG event
        SEND alert
    ELSE:
        MARK as normal

    LOG event and prediction

--------------------------------
MONITORING
--------------------------------
TRACK anomaly trends
TRACK drift metrics
TRIGGER alerts if thresholds exceeded

END
```
