# Airborne-emssion-demo

Aeromon BH-12 measurement devices have been installed on trams in Helsinki to collect data on air quality. Some datasets are publicaly available on the Helsinki Open data service, aiming to make bette use of public data. I have downloaded soem of the datasets for exploration and basic ML analysis with regression and clustering. Four sets of devices were used, there isntalled on the trams (moving) and the fourth at a fixed location (supersite).

The dataset has been downloaded from Helsinki Region Infoshare service on 09.11.2025 under the license Creative Commons Attribution 4.0.

The datasets contain raw and processed files.
The raw data have been processed to reduce hte noise, as explained in the data repository: 
* Data including artefacts deriving from sensor power cycles has been removed.
* Sensor offset level (0 level) drift caused by temperature and humidity effects has been compensated.
* Sensor noise level has been filtered slightly to remove signal alteration which derives from effects not connected to sensor response towards gas concentration change.
  

The columns in the procseesed files represent: 
timestamp = time in seconds (starting from '1970-01-01 00:00:00')
spora-id = specifying the tram in which the devices were installed
latitude = latitude coordinate
longitude = longitude coordinate
NO = nitric oxide
NO2 = nitrogen dioxide
O3 = ozone
CO = carbon oxide
BME680_pressure = air pressure measured using BME680 sensor
BME680_humidity = humidity measured using BME680 sensor
BME680_temperature = temperature measured using BME680 sensor
Comment

## Project aim 
This project explores real-world air quality sensor data from Helsinki, applying simple modeling and visualization techniques
to understand how pollutant concentrations vary with time and conditions.

## Project features 
### Features
- Data cleaning and preprocessing (handling missing and noisy data)
- Regression model predicting NO₂ levels from temporal features
- Visualization of trends and emission-like patterns
- Tools: Python, Pandas, scikit-learn, Matplotlib
