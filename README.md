# UBER-analysis
Using Plotly and Python to do some analysis of Uber data from 2014 and 2015

# Context
The goal of this project was to analyze a large dataset of Uber ride data from New York City to uncover valuable insights into urban mobility patterns. Understanding peak hours, frequent routes, and areas of high demand is crucial for optimizing ride-sharing services and improving urban transportation efficiency. This analysis aimed to transform raw trip data into actionable intelligence.

# Actions & Techniques Applied
Data Acquisition and Loading:

Six separate CSV files (uber-raw-data-apr14.csv to uber-raw-data-sep14.csv) for Uber pickups in New York City from April to September 2014 were loaded into pandas DataFrames.

An additional dataset (uber-raw-data-janjune-15.csv) for January-June 2015 was loaded for comparative analysis.

# Data Preprocessing and Transformation:

All 2014 DataFrames were concatenated into a single master DataFrame (df_union) to consolidate the data for comprehensive analysis.

The 'Date/Time' column was converted to datetime objects to enable time-based analysis (e.g., extracting hour of day, date, and time components).

A new 'hour_of_day' column was created from the 'Date/Time' column to facilitate hourly trip analysis.

'Date' and 'Time' columns were extracted from 'Date/Time' for further time-series analysis.

Base codes (e.g., 'B02512', 'B02764') were replaced with more descriptive names ('Unter', 'Danach-NY', etc.) using a mapping dictionary for better readability and interpretation.

Similar preprocessing steps were applied to the 2015 dataset, including setting 'Pickup_date' as the index and creating 'Date' and 'Time' columns.

# Exploratory Data Analysis (EDA) & Visualization:

Hourly Trip Analysis:

Trip counts were aggregated by hour_of_day to identify peak and off-peak hours.

A line plot was generated using matplotlib.pyplot to visualize the total number of trips aggregated across all days for each hour of the day.

Daily Trip Analysis:

Trip counts were aggregated by Date (daily) to observe daily trends.

Line plots were created to visualize daily trip counts for both 2014 and 2015 data, allowing for trend comparison between years.

Monthly Trip Analysis:

Trip counts were aggregated by Month to identify monthly patterns and growth.

Line plots were generated to show total trips per month for both 2014 and 2015, highlighting seasonal variations or overall demand changes.

Base Location Analysis:

The number of trips originating from each dispatching base was calculated.

A bar chart was generated to visualize the count of trips per base location, identifying the busiest dispatching hubs.

Geospatial Analysis (Heatmaps):

plotly.express was used to create an interactive scatter map of pickup points for Uber rides in 2014.

The map visualized latitude and longitude data, with points sampled for performance and rendered with partial opacity to show areas of higher density, effectively creating a demand heatmap.

# Results
Peak Hours: The analysis revealed distinct peak hours for Uber trips, with demand significantly increasing in the late afternoon and early evening (around 4 PM to 8 PM) on aggregated data for both 2014 and 2015.

Daily and Monthly Trends: Daily trip counts showed fluctuations, while monthly trends indicated a general increase in Uber ridership from April to September in 2014, and similar growth trends in 2015, suggesting expanding service adoption.

Frequent Routes / High-Demand Areas: The interactive scatter map highlighted geographical clusters of pickup points, visually indicating high-demand areas in New York City. These heatmaps provide insights into where Uber demand is concentrated, which could inform driver positioning and service expansion strategies.

Busiest Dispatching Bases: Specific dispatching bases were identified as handling a significantly higher volume of trips, offering insights into operational hubs and potential areas for resource allocation optimization.
