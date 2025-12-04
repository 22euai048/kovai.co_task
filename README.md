Public Transport Passenger Forecasting

Dataset Overview

This dataset contains daily passenger journey counts segmented by service types over multiple years. It records how many passengers used each of the following public transport services on each day:
Local Route: Serves local neighborhoods with frequent stops.
Light Rail: Medium distance urban rail service.
Peak Service: Services running during peak commute hours.
Rapid Route: Express or limited-stop routes for faster travel.
School: Dedicated journeys corresponding to school travel schedules.
Other: Any other types of public transport services in the data.
Each data record includes the date and integer counts of passengers for these service types.

PROCESS:
>>Understanding the Problem & Dataset
>>Choosing the Right Model
>>Data Preparation
>>Model Fitting
>>Forecasting
>>Deriving Insights
>>Visualization
>>Operational Interpretation

Why ARIMA is used here

>>DAILY TIME SERIES → ARIMA's specialty

>> DAY-TO-DAY DEPENDENCIES → Captured by AR(1) term (p=1)

>>TRENDS (school terms, seasonal) → Handled by differencing (d=1)

>> RANDOM SHOCKS (strikes, weather) → Smoothed by MA(1) term (q=1)

>> 7-DAY OPERATIONAL HORIZON → ARIMA's sweet spot

>> SERVICE-SPECIFIC PATTERNS → Separate models per service

ARIMA BREAKDOWN
p = 1: Uses yesterday’s passenger change to capture daily momentum (e.g., Monday’s demand affecting Tuesday).
d = 1: Removes steady growth or decline, allowing the model to focus on daily fluctuations.
q = 1: Smooths shocks from the previous day, handling irregular events like strikes or road closures.

 WHAT ARIMA DOES HERE? 
1. FORECASTS → Predicts next 7 days per service
2. LEARN PATTERNS → Finds daily/weekend trends  
3. SMOOTH NOISE → Ignores random shocks
4. GIVE INSIGHTS → Reveals business truths



INSIGHT 1:
Graph is a Predictability League Table for different transport services.
Each dot represents a service type (School, Peak Service, Local Route, Rapid Route, Light Rail).
The x-axis shows the Stability Score.
Services on the right have higher stability → easier for the model to predict.
Services on the left have lower stability → harder to predict.

The vrtical list simply ranks each service, and the horizontal distance shows how stable or unstable they are.

INSIGHT 2:
Different services have different levels of predictability.

Some services run with steady patterns every day : these are easy for ARIMA to forecast.
Some services have lots of ups and downs : these are hard for the model to predict.

INSIGHT 3:
Graph compares how long each service “remembers” a shock: a sudden spike or drop in demand.
Each service has:
A grey dot = No memory baseline at 0
A purple dot = its actual AR(1) shock memory value

Whether the AR(1) coefficient is positive, negative, or close to zero

INSIGHT 4:
This insight tells you how people might change the type of service they use, not just how many people travel.
Adjusted color densities based on the peaks and the return 

INSIGHT 5:
This insight tells you how certain or uncertain the model is about each service’s next-7-day forecast.



