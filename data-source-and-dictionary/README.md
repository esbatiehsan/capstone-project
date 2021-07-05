# Data Source and Dictionary

### Data Source
The majority of data used in this project was acquired from two separate sources.

National Climatic Data Center was the source of hourly weather data. This [dataset](https://www.ncei.noaa.gov/metadata/geoportal/rest/metadata/item/gov.noaa.ncdc:C00532/html) can be accessed for different stations via the official API.

Airline on-time performance data was sourced form the Bureau of Transportation Statistics via its [website](https://www.transtats.bts.gov/DL_SelectFields.asp?gnoyr_VQ=FGJ&QO_fu146_anzr=b0-gvzr).

### Data Dictionary
The columns for my dataset are as follows:
<ul>
  <li>origin: unique identifier code for origin airport</li>
  <li>latitude: latitude of the origin airport</li>
  <li>longitude: longitude of the origin airport</li>
  <li>elevation: elevation on the origin airport, metres</li>
  <li>carrier: unique identifier code for operating airline</li>
  <li>tail_num: unique identifier for airliner used in a flight</li>
  <li>precipitation: amount of liquid precipitation for each observation, millimetres</li>
  <li>condition: reported weather condition for each observation</li>
  <li>cloud_base: minimum cloud altitude reported for each observation, metres</li>
  <li>dew_temp: dew point temperature reported for each observation, degrees celsius</li>
  <li>pressure: sea-level pressure reported for each observation, hPa</li>
  <li>air_temp: air temperature reported for each observation, degrees celsius</li>
  <li>visibility: horizontal distance reported for each observation, metres</li>
  <li>wind_speed: wind speed reported for each observation, metres per second</li>
  <li>wind_direction: wind dircetion reported for each observation</li>
  <li>dep_delay: total time each flight was delayed by at departure, minutes</li>
  <li>carrier_delay: total time each flight was delayed by because of carrier issues, minutes</li>
  <li>extreme_weather_delay: total time each flight was delayed by because of extreme weather events, minutes</li>
  <li>weather_delay: total time each flight was delayed by because of normal weather events, minutes</li>
  <li>nas_delay: total time each flight was delayed by because of national aviation system events, minutes</li>
  <li>security_delay: total time each flight was delayed by because of security events, minutes</li>
  <li>lat_aircraft_delay: total time each flight was delayed by because of late aircraft arrival, minutes</li>
  <li>cancelled: whether flight was cancelled or not</li>
  <li>cancellation_code: unique identifier indicating why flight was cancelled</li>
  <li>diverted: whether flight was diverted to another airport or not</li>
  <li>destination: unique identifier code for destination airport</li>
  <li>arr_delay: total time each flight was delayed by at arrival, minutes</li>
  <li>air_time: total time each flight was in the air, minutes</li>
  <li>distance: total distance between origin and destination, kilometres</li>
  <li>dep_15_del: binary label indicating whether departure was delayed by more than fifteen minutes or not</li>
  <li>month: scheduled month of flight</li>
  <li>day: scheduled day of flight</li>
  <li>day_of_week: scheduled weekday of flight</li>
  <li>hour: scheduled hour of flight</li>

It is important to mention that not all these columns were used for modelling the data as some are highly correlated with the target variable, while others offered no additional information when considering departure delays.
