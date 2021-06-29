# Data Science Immersive Capstone Project - General Assembly
This project was the main requirement for the successful completion of the Data Science Immersive course at General Assembly London.

## Predicting Delay Based on Flight and Weather Features
Air travel is an indispensable feature of the modern world. It permeates our economic, social, and leisure activities. It connects us on a national, regional, and global scale. It generates trade, creates employment opportunities, and expedites tourism. Given this central and consequential role, any disruption can have major impacts. For example, the Federal Aviation Authority reported that disruptions caused by flight delays had cost the US economy $33 billion in 2019 alone.

The aim of this project is to use the data available from different authorities in the United States to provide a model that would enable different stakeholders, including passengers, and airline and airpot operators to predict possible departure delays and implement measures that would either eliminate the possibility of such delays or alleviate their effects.

Given how large the domestic network is in the United States, and the geographical and climatic differences that play out on a continental scale, I decided to limit my data acquisition to the twenty busiest airports in the country by number of departures. I also decided to follow the industry standard and label a flight as delayed if the amount of time it was delayed by exceeded 15 minutes.

The raw data was acquired from three different sources. Airline on-time performance data is available from the Bureau of Transport Statistics for all domestic flights from 1987 onwards, while historical weather data for the twenty busiest departure airports was download through the official API provided by the National Climatic Data Center. Additional weather data was obtained through Meteostat Python library.
