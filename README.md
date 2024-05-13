## Unlocking Insights: Exploring Citi Bike Ridership Patterns

The project aims to provide a comprehensive analysis of the Citi Bike program in New York City, spanning from April 2023 to March 2024. Through data visualization and interpretation, the analysis seeks to uncover key insights into bike usage patterns, popular routes and seasonal variations. These insights will enable stakeholders to make informed decisions regarding resource allocation, infrastructure development, and marketing strategies to enhance the overall efficiency and effectiveness of the Citi Bike program.

View Tableau Dashboard website here: https://vanillatyy1.github.io/18_Citibike/

## About the Dataset 
Citi Bike stands as the nation's largest bikeshare program, boasting 25,000 bikes and a network of over 1,500 stations spanning Manhattan, Brooklyn, Queens, the Bronx, Jersey City, and Hoboken. Offering the convenience of unlocking bikes from one station and returning them to any other within the system, Citi Bike facilitates seamless urban transportation.

Since its inception in 2013, the Citi Bike program has established a robust infrastructure for data collection, meticulously gathering information on program utilization. Monthly, comprehensive bike data is compiled, organized, and made publicly accessible through the Citi Bike DataLinks portal at https://citibikenyc.com/system-data.

This report explores the monthly data specific to Jersey City, covering the period from April 2023 to March 2024. Its objective is to offer insights into ridership growth, identify the most popular starting and ending locations for journeys, and analyze peak usage hours during both summer and winter months.

## Observation About the Dataset
During the creation of the map visualization, I noticed a discrepancy where multiple latitude and longitude values were linked to the same station ID.

Additionally, some of the coordinates were plotting stations in the middle of the water. To address this, I attempted to refine the dataset by creating a master dataframe with only unique station names and IDs. I calculated the average latitude and longitude coordinates, rounding them down to six decimals, in an effort to display one dot per station ID on the map. However, upon reviewing the resulting dataframe, I found that at least 112 values had latitude and/or longitude coordinates with less than six decimals. Further investigation revealed that some station IDs in the original file did not have six decimal places to begin with.

To overcome these challenges, I decided to take a different approach. I exported the concatenated dataset with dropped NA values and loaded it into Tableau. I drew average coordinates without rounding down and filtered out stations with significantly fewer riders, focusing on the top 10 stations. To ensure accurate mapping, I intend to manually search for the proper latitude and longitude coordinates that match the stations using Google Maps or another advanced method. However, due to time constraints, this step will be a project for the future.

Additionally, I noticed that there are multiple ride IDs where the start station is the same as the end station. This suggests that riders may be testing out bikes or completing round trips. While this is understandable from a privacy perspective, as the dataset contains unique ride IDs, it does not provide insight into demographic data or whether multiple ride IDs belong to the same member or person.

