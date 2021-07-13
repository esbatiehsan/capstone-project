# Data Science Immersive Capstone Project - General Assembly
This project was the main requirement for the successful completion of Data Science Immersive program at General Assembly, London. In this repository you can find all the notebooks related to this project, plus further analysis and conclusions.

## Predicting Delay Based on Flight and Weather Features
Air travel is an indispensable feature of the modern world. It permeates our economic, social, and leisure activities. It connects us on a national, regional, and global scale. It generates trade, creates employment opportunities, and expedites tourism. Given this central and consequential role, any disruption can have major impacts. For example, the Federal Aviation Administration reported that disruptions caused by flight delays had cost the US economy $33 billion in 2019 alone.

The aim of this project is to use the data available from different official sources in the United States to provide a model that would enable different stakeholders, including passengers, and airline and airpot operators to predict possible departure delays and implement measures that would either eliminate the possibility of such delays or alleviate their effects.

The raw data was acquired from three different sources. Airline on-time performance data is available from the Bureau of Transportation Statistics for all domestic flights from 1987 onwards, while historical weather data for each departure airport was downloaded through the official API provided by the National Climatic Data Center. Additional weather data was obtained through Meteostat Python library.

Given how large the domestic network is in the United States, and the geographical and climatic differences that play out on a continental scale, I decided to limit my data acquisition to the twenty busiest airports in the country by number of departures. I also decided to follow the industry standard and label a flight as delayed if the amount of time it was delayed by exceeded 15 minutes.

Each entry in my dataset contains the information related to a single operation, including flight and weather features.

### Repository Content:

#### **[Data Source and Dictionary](./data-source-and-dictionary)**

Access to the two major sources of data I used in this project and also a short description for each of the columns present in the cleaned dataset.

#### **[Data Acquisition and Cleaning](data-acquisition-cleaning.ipynb)**

You can use this link to access the code for downloading the raw data and cleaning it.

#### **[Exploratory Data Analysis](exploratory-data-analysis.ipynb)**

This notebook contains the code and the analysis of data.

#### **[Optimum Data Size](optimum-data-size.ipynb)**

This link gives you access to a quick study of the effect of training data size on model score and scalability.

#### **[Modelling](modelling.ipynb)**

Follow this link to access the modelling section of this project.

#### **[Analysis and Conclusions](./analysis-and-conclusions)**

A brief discussion of methods used and choices made during this project and a look at future ideas to take it forward.
