Technical Report: 
ARIMA for Public Transport Passenger Forecasting

Purpose of the Model
Forecasting passenger demand helps public transport operators plan vehicles and staff efficiently, avoiding overcrowding or underutilization. The dataset captures daily journeys by service type, which exhibits trends, seasonality, and random fluctuations. 
The model must:
Learn from past values (time dependencies)
Adjust for trends to prevent bias
Account for random shocks

Why ARIMA(1,1,1)
ARIMA (AutoRegressive Integrated Moving Average) models momentum, trends, and noise:

p=1 (AR term): Captures dependency on recent days, reflecting day-to-day momentum.

d=1 (Differencing): Removes trends to stabilize the series.

q=1 (MA term): Smooths out recent shocks and noise.

Separate models were fit for each major service using the last 180 days to focus on recent patterns, producing interpretable 7-day forecasts.

Key Insights & Visualizations

>>Predictability Score

Measures stability of forecasts via residuals.

Visualization: Residual plot showing low variance → reliable forecasts.


>>Shock Memory

AR(1) coefficient indicates how long demand is affected after unusual events.

Visualization: Coefficient trend showing decay after disruptions.


>>Pressure Index

Forecasted daily totals normalized by 95th percentile of historical peaks → signals potential overload.

Visualization: Forecast vs historical peaks highlighting high-pressure days.


>>Mode Switching Risk

Compares forecasted passenger share between Local and Rapid modes vs historical shares.

Visualization: Stacked bar chart showing changes in mode preference.


>>Forecast Uncertainty

95% prediction intervals quantify confidence and guide flexible resource allocation.

Visualization: Forecast plot with shaded confidence intervals.


Practical Implications

Identify reliably forecastable vs volatile lines.

Estimate recovery periods after disruptions.

Predict high-demand days for better scheduling.

Detect shifts in travel patterns for tactical route adjustments.

Allocate resources efficiently based on forecast confidence.

Conclusion
ARIMA(1,1,1) provides accurate, interpretable, and operationally relevant short-term forecasts for public transport demand. Its insights allow proactive planning and better service management.
