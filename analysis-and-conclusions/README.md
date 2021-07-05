# Analysis and Conclusions

### Data Acquisition and Cleaning
Through out this project, accessing and downloading the necessary data was perhaps the most straight forward task. My two main data sources, Bureau of Transport Statistics (BTS) and National Climatic Data Center (NCDC), provide well structured datasets with ample documentation for both accessing the raw data and defining the various features. The only inconvenience at this stage was the lack of an AIP for accessing the BTS dataset which had to be done via a menu system.

Nonetheless, cleaning the raw data still posed some challenges, especially the data acquired from NCDC dataset. I decided to use make use of the information available from the Global Hourly Data dataset in order to have the maximum possible data resolution. Once the API request link was constructed and first batch of dat downloaded, I realised there are some issues. To begin with, different stations report their hourly figures at different times. For example, one station reports at 52 minutes passed the hour, while another reports at 54 minutes passed the hour. This had to be accounted for when automating the cleaning process.

The data also contained information related to other aspects of each recording, mixed with the actual data, and presented as strings. For example, the amount of liquid precipitation at a given time and place was presented as "00,0000,0,0". The four different fields separated my comma represent, from left to right, Period Quantity, Depth Dimension, Condition Code, Quality Code. They have the following definitions:
<ul>
    <li>Period Quantity: The quantity of time over which the liquid precipitation was measured.</li>
    <li>Depth Dimension: The depth of liquid precipitation that is measured at the time of each observation, in millimetres.</li>
    <li>Condition Code: The code that denotes whether a liquid precipitation depth dimension was a trace value.</li>
    <li>Quality Code: The code that denotes a quality statues of the reported liquid precipitation data.</li>
</ul>

This pattern is repeated for almost every other feature, and represents additional challenges. First, apart form the hourly data, there were some additional aggregate data too. While the hourly observations all had "01" in their first field, the aggregate observations had, for example, "03". Given that I had no need for these aggregated information, I had to find and delete them from my data. It was also necessary to extract the actual dimension data and turn it into a float value for later use.

Next, it became apparent that some observations were completely missing, perhaps as a result of equipment failure. Consequently, I had to find all these instances and insert them into the data with each feature indicating a missing value to begin with. To deal with the missing data, I followed a two-stage approach. First, I used the Meteostat Python library to replace some of the missing data. For the reminder, I used a KNNImputer for the continuous features and a DecisionTreeClassifier for the categorical features, trained using the available data.

The carrier on-time performance data downloaded form BTS website was far more straight forward to work with. The only noteworthy issue was the extraction of weather related delays from National Aviation System delays. This was done using the monthly nationwide percentage provided by BTS. Unfortunately, no further granular data was available.

Once the two separate sets were prepared, they were joined together to form a single dataset. You can refer to the Data Dictionary page for a complete breakdown of all individual columns.

### Data Exploration
While exploring the data I quickly realised there are no large correlation between the binary labels and the various weather and flight related features. For example, wind speed is a major cause of flight delay as high winds make both take-off and landing tricky, but the data showed there is minimal separation between wind speeds related to the two labels.

The highest correlation can be seen between the labels and the reported weather condition, with snowfall and heavy snowfall resulting in highest percentage of delayed flights, followed by thunderstorms with different strengths. Meanwhile, delays caused by various intensity of rainfall follows the overall average.

One interesting weather feature turned out to be wind direction which has a strong local element to it, with different airports reporting different fraction of delays for different wind directions.

Considering the flight related features, only the scheduled hour of flight displays a clear pattern when it comes to fraction of flights that were delayed, with a gradual increase in delayed flights as we move towards early evening. Other features such as scheduled month and day of flight show much less obvious trends.
