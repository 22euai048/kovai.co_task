Technical Report: 
Using ARIMA for Public Transport Passenger Forecasting
Why I Created This Model?
Forecasting public transport demand helps plan vehicle and staff allocation efficiently, avoiding overcrowding or wasted resources. The dataset contains daily passenger journeys by service type, showing complex temporal patterns: trends, seasonality, shocks.

To address these, I needed a model that can:

Understand how demand depends on past values (time dependencies)

Handle trends to avoid over/under prediction

Capture random fluctuations and shocks

Why I Chose ARIMA(1,1,1)
ARIMA is a classical, yet powerful statistical model designed for time series with these exact characteristics.

The p=1 (autoregressive) term makes forecasts depend on recent changes, capturing day-over-day momentum.

The d=1 (differencing) term removes trends, stabilizing the data for modeling.

The q=1 (moving average) term accounts for shock and noise smoothing from recent days.

I fit separate ARIMA(1,1,1) models for each major service on the last 180 days to focus on recent behavior, producing accurate and interpretable 7-day forecasts.

Insights Produced and How the Model Brings Them
Predictability Score:
Derived from the ARIMA residuals (model errors). Small residuals relative to mean demand mean forecasts are stable and reliable. It tells which services can be trusted most.

Shock Memory:
Measured by AR(1) coefficient in ARIMA, indicating how long demand is affected after an unusual event. It helps in understanding recovery time after disruptions.

Pressure Index:
Normalizes forecasted daily totals by the 95th percentile of highest historical demand days, signaling whether upcoming days are expected to be near peak loads.

Mode Switching Risk:
By comparing forecasted passenger share between Local and Rapid modes against historical shares, it indicates changes in travel behavior (e.g., more neighborhood trips).

Forecast Uncertainty:
Using the model’s 95% prediction intervals, it quantifies uncertainty relative to forecast levels, signaling where operational flexibility is needed.

What This Means Practically
This ARIMA-based approach doesn’t just produce numbers. It uncovers meaningful, actionable stories behind the data:

Which lines are reliably forecastable and which require cautious planning.

How long disruptions influence demand for better post-event decisions.

When the upcoming week will be normal or unusually busy.

Whether travel patterns are shifting, implying tactical route adjustments.

How confident we can be in each forecast to wisely allocate resources.

In sum, ARIMA(1,1,1) gives an excellent balance of forecasting accuracy, interpretability, and operational relevance for short-term public transport demand forecasting.