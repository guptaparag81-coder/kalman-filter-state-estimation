# Kalman Filter State Estimation - Learning Notes

Author: Parag Gupta

---

# 1. Purpose of the Project

The purpose of this project is to recover the true state of a system from noisy measurements.

Examples:

- Asset prices
- GPS locations
- Sensor readings
- Temperature measurements
- Methane emission estimates

---

# 2. What is a Kalman Filter?

A Kalman Filter is a recursive estimation algorithm.

It combines:

- Model predictions
- Sensor measurements

to estimate the most likely true state.

---

# 3. Why Not Use Simple Averaging?

A moving average smooths noise but also removes useful dynamics.

The Kalman Filter adapts continuously and balances:

- Trust in measurements
- Trust in the model

---

# 4. State Estimation

State estimation means estimating a hidden variable from observations.

Examples:

- True stock price
- True object position
- True temperature

---

# 5. Prediction Step

Code:

```python
x_pred = x_est
P_pred = P + Q
```

Purpose:

Predict the next state before seeing a measurement.

---

# 6. Update Step

Code:

```python
K = P_pred/(P_pred+R)

x_est = x_pred + K*(z-x_pred)
```

Purpose:

Combine prediction and measurement.

---

# 7. What is Kalman Gain?

Kalman Gain controls how much the filter trusts measurements.

K close to 1:

Trust sensor more.

K close to 0:

Trust model more.

---

# 8. Process Noise (Q)

Process noise represents uncertainty in system dynamics.

Large Q:

State changes rapidly.

Small Q:

State changes slowly.

---

# 9. Measurement Noise (R)

Measurement noise represents sensor uncertainty.

Large R:

Measurements are unreliable.

Small R:

Measurements are trusted.

---

# 10. Mean Squared Error (MSE)

Measures estimation accuracy.

Lower MSE indicates better state recovery.

---

# 11. Applications

Kalman Filters are widely used in:

- Finance
- Robotics
- Aerospace
- Navigation
- Environmental Monitoring
- Signal Processing

---

# 12. Overall Workflow

True Signal
↓
Add Noise
↓
Noisy Measurements
↓
Kalman Filter
↓
State Estimation
↓
MSE Evaluation
↓
Visualisation

---

# Interview Summary

"I implemented a Kalman Filter in Python to estimate hidden states from noisy measurements. The project demonstrates recursive state estimation, uncertainty modelling, signal denoising, and optimal measurement fusion. The filter significantly reduced estimation error compared with raw observations."
