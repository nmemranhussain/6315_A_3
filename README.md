# Predictive Modeling of Bikeshare Demand: A Study on Capital Bikeshare
This project analyzed Capital Bikeshare data using Linear, Ridge, LASSO, Elastic Net, KNN, Regression Tree, Random Forest, Gradient Boosting, and Neural Network models to forecast ridership and improve operational efficiency.

### Basic Information

* **Person or organization developing model**: N M Emran Hussain `nmemran.hussain@gwu.edu`
* **Model date**: March, 2025
* **Model version**: 1.0 
* **License**: [Apache License 2.0](https://github.com/nmemranhussain/RML_A_1_Group_11/blob/main/LICENSE)
* **Model implementation code**: [Assignment](https://github.com/nmemranhussain/6315_A_3/blob/main/6315_A_3_final.ipynb)
* **Final report**: [Final Report](https://github.com/nmemranhussain/6315_A_3/blob/main/6315_A_3_final_report.pdf)

### Training Data

* Data dictionary: 

| Name | Modeling Role | Measurement Level| Description |
|------|---------------|------------------|-------------|
| Date	| Input	| Date	| Date of observation |
| Datetime |	Input	| Date	| Date of observation |
| Tempmax	| Input	|Interval	|Maximum daily temperature (°F) |
| Tempmin	| Input	| Interval	| Minimum daily temperature (°F) |
| Temp	| Input	| Interval	| Average temperature (Â°F) |
| Feelslikemax	| Input	| Interval	| Maximum feels-like temperature (Â°F) |
| Feelslikemin	| Input	| Interval	| Minimum feels-like temperature (Â°F) |
| Feelslike	| Input	| Interval	| Average feels-like temperature (Â°F) |
| Dew	| Input	| Interval	| Dew point temperature (Â°F) |
| Humidity	| Input	| Interval	| Humidity percentage |
| Precip	| Input	| Interval	| Total daily precipitation (inches) |
| Precipprob	| Input	 | Interval	| Probability of precipitation (%) |
| Precipcover	| Input	| Interval	| Proportion of the day with precipitation (0 to 1 scale) |
| Snow	| Input	| Interval	| Daily snowfall amount (inches) |
| Snowdepth	| Input	| Interval	| Snow depth on the ground at day's end (inches) |
| Windspeed	| Input	| Interval	| Wind speed (mph) |
| Winddir	| Input	| Interval	| Wind direction (degrees) |
| Sealevelpressure	| Input	| Interval	| Sea level pressure (hPa) |
| Cloudcover	| Input	| Interval	| Cloud cover (%) |
| Visibility	| Input	| Interval	| Visibility (miles) |
| Solarradiation	| Input	| Interval	| Solar radiation (W/mÂ²) |
| Solarenergy	| Input	| Interval	| Solar energy (MJ/mÂ²) |
| Uvindex	| Input	| Interval	| UV index |
| Moonphase	| Input	| Interval	| Moon phase (0=new, 1=full) |
| Icon	| Input	| Nominal	| Weather icon for the day |
| Which_High | Output | Categorical | Whether Pickups or Drop-offs are higher on a given day (PU_High or DO_High) |

- **Source of Taining Dataset Name:** Capital Bikeshare Data ('202402-capitalbikeshare-tripdata.csv', '202403-capitalbikeshare-tripdata.csv', '202404-capitalbikeshare-tripdata.csv' & 'DC_weather_2024.csv')  
- **Number of Samples:** 318689, 436947, 490266 & 367  
- **Features Used:** Temporal Features (hour, weekday, months), Weather Features (temp, precip, windspeed, uvindex, icon), Station Usage Features (Pickup count and Drop-off count)
- **Target variable Used:** Pickup count (PU_ct) and Drop-off count (DO_ct)
- **Data Source:** [capitalbikeshare-data](https://s3.amazonaws.com/capitalbikeshare-data/index.html)
- **How training data was divided into training and test data**: Training (60%) and testing (40%).
- **Type of model**: Linear, Ridge, LASSO, Elastic Net, KNN, Regression Tree, Random Forest, Gradient Boosting and Neural Network
- **Software used to implement the model**: Python, numpy, scikit-learn
- **Version of the modeling software**: numpy: 2.0.2, pandas: 2.2.2, matplotlib: 3.10.0, Python 3.11.12, scikit-learn version: 1.5.1

### Evaluation Metrics

- **Mean Squared Error (MSE):** Here MSE is used for both Number of bike pickups (PU_ct) and Number of drop-offs or dock availability (DO_ct). It measures average squared differences between actual and predicted values. Lower MSE indicates better prediction accuracy.
- **Out-of-Sample Cost:** A custom business-oriented metric reflecting operational decision cost (e.g., misallocation or imbalance). If a model has a higher MSE, it might still produce better real-world outcomes based on this cost.
- **Visual Evaluation (Charts/Plots):** Line plots and bar charts were used to compare prediction errors across models and to zoom into subtle differences in out-of-sample cost. It helps us to assess model visual effectiveness for decision-making.

### Quantitative Analysis

| Model Name | Hyperparameter tuning of the models | MSE of PU_ct | MSE of DO_ct | Out-of-sample-cost |
|------------|------------------------------------|---------------|-------------|--------------------|
| Linear Regression | - | 54.8884 | 69.5465 | 76.6389 |
| Ridge | Alpha = 100 | 54.8891 | 69.5454 | 76.6389 |
| LASSO | Alpha =  10 | 71.5580 | 79.7125 | 76.6389 |
| Elastic Net | Alpha = 100 | 62.5541 | 72.4992 | 76.6389 |
| Decision Tree | max_depth = 1 | 86.3950 | 95.9265 | 76.6389 |
| Random Forest |  Best Parameters for PU_ct: {'max_depth': 5, 'min_samples_split': 10, 'n_estimators': 200} Best Parameters for DO_ct: {'max_depth': 5, 'min_samples_split': 10, 'n_estimators': 200} | 73.1887 | 85.3664 | 76.5833 |
| KNN |  | 64.9297 | 72.8519 | 76.6389










