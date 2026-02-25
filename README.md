# F1-MachineLearning-LapTimePrediction (Cache Not Included)

Key Features
Physics-Based Feature Engineering:

Tyre Life: Models the non-linear degradation of tires over time.

Fuel Load: Estimates the lap time gain as the car becomes lighter (fuel burn).

Track Condition: Filters out "dirty" data like Pit Stops, Safety Car laps, and Yellow Flags.

XGBoost Regression: Uses gradient boosting to capture complex interactions between tire compound, track evolution, and driver pace.

Drift Calibration: Calculates the performance delta between 2023 and 2024 Qualifying sessions to scientifically correct the model's predictions for the new season's car performance.

Tech Stack
Python: Core logic.

FastF1: Telemetry and timing data acquisition.

XGBoost: Machine Learning regressor.

Pandas/NumPy: Data manipulation and feature extraction.

Matplotlib/Seaborn: Visualization of Actual vs. Predicted pace.

Results
Baseline Error (Uncalibrated): 1.53 seconds (MAE).

Diagnosis: The model successfully predicted the race "rhythm" (tire wear) but consistently predicted slower times because it was trained on the slower 2023 car.

Final Error (Calibrated): 1.02 seconds (MAE).

Improvement: Applying the Qualifying Offset reduced the prediction error by ~33%, proving that historical data requires calibration to remain relevant for future predictions.
