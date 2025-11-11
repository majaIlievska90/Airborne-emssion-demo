# Airborne-emssion-demo

Aeromon BH-12 measurement devices have been installed on trams in Helsinki to collect data on air quality. Some datasets are publicaly available on the Helsinki Open data service, aiming to make bette use of public data. I downloaded some of the datasets for exploration and basic ML analysis with regression and clustering. Four sets of devices were used, three installed on the trams (moving) and the fourth at a fixed location (supersite).

The datasets have been downloaded from Helsinki Region Infoshare service on 09.11.2025 under the license Creative Commons Attribution 4.0.

The datasets contain raw and processed files.
The raw data have been processed to reduce hte noise, as explained in the data repository: 
* Data including artefacts deriving from sensor power cycles has been removed.
* Sensor offset level (0 level) drift caused by temperature and humidity effects has been compensated.
* Sensor noise level has been filtered slightly to remove signal alteration which derives from effects not connected to sensor response towards gas concentration change.
  

The columns in the procseesed files represent:\
timestamp = time in seconds (starting from '1970-01-01 00:00:00')\
spora-id = specifying the tram in which the devices were installed\
latitude = latitude coordinate\
longitude = longitude coordinate\
NO = nitric oxide\
NO2 = nitrogen dioxide\
O3 = ozone\
CO = carbon oxide\
BME680_pressure = air pressure measured using BME680 sensor\
BME680_humidity = humidity measured using BME680 sensor\
BME680_temperature = temperature measured using BME680 sensor\
Comment

## Project aim 
This project explores real-world air quality sensor data from Helsinki, applying simple modeling and visualization techniques
to understand how pollutant concentrations vary with time and what are other conditions that affect them.

## Project features 
### Features
- Data processing: reading files from one month, both moving and supersite; handling negative values; changing the format of the timestamp; concatenating and exploring the data.
- Bar plot of the emssions of NO, CO2 and O3 across hours of the day, for each day. By visually exploring this plots, O3 concentrations appear higher during early morning hours. CO2 concentrations appear higher during the day, while NO emmisions seem more uniform throughout the day. 
- Regression model predicting NO₂ levels from the remaining features.
  - I tested different sets of predictors, and the combination of the measurement station data (moving and superstation) increased the coefficient of determination, R². Due to high-frequency spatial variability in mobile sensor data and the effect of the direct emissions sources, simple linear models based on temperature, humidity, hour-of-day  etc., do not fully capture pollutant fluctuations, resulting in smaller R² values (< 0.5). RMSE remains low due to the small magnitude of measured concentrations. Among the predictor variables, ozone concentration have the largest effect on the NO emissions (coefficient 2.07). 
- Visualization of the measured and predicited NO concentrations.
- PCA of the independant variables in the regression model, and k-means clustering. The points in the PCA were finally colored based on the cluster assignment. This can helpe further exploration of the effect on the the different measurements on the variable of interest. 
- Tools: Python, Pandas, scikit-learn, Matplotlib
