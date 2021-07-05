# Analysis and Conclusions

### Data Acquisition and Cleaning
Through out this project, accessing and downloading the necessary data was perhaps the most straight forward task. My two main data sources, Bureau of Transport Statistics (BTS) and National Climatic Data Center (NCDC), provide well structured datasets with ample documentation for both accessing the raw data and defining the various features. The only inconvenience at this stage was the lack of an AIP for accessing the BTS dataset which had to be done via a menu system.

Nonetheless, cleaning the raw data still posed some challenges, especially the data acquired from NCDC dataset. I decided to use make use of the information available from the Global Hourly Data dataset in order to have the maximum possible data resolution. Once the API request link was constructed and first batch of dat downloaded, I realised there are some issues. To begin with, different stations report their hourly figures at different times. For example, one station reports at 52 minutes passed the hour, while another reports at 54 minutes passed the hour. This had to be accounted for when automating the cleaning process.

The data also contained information related to other aspects of each recording, mixed with the actual data, and presented as strings. For example, the amount of liquid precipitation at a given time and place was presented as "01,0000,0,0". The four different fields separated my comma represent, from left to right, Period Quantity, Depth Dimension, Condition Code, Quality Code. The have the following definitions:
<ul>
    <li>Period Quantity: The quantity of time over which the liquid precipitation was measured.</li>
    <li>Depth Dimension: The depth of liquid precipitation that is measured at the time of each observation.</li>
    <li>Condition Code: The code that denotes whether a liquid precipitation depth dimension was a trace value.</li>
    <li>Quality Code: The code that denotes a quality statues of the reported liquid precipitation data.</li>
</ul>
First, apart form the hourly data, there were some additional aggregate data too, such as 3, 6, and 24-hourly aggregates. These had to be discovered and dropped.
