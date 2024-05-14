## Unlocking Insights: Exploring Citi Bike Ridership Patterns

The project aims to provide a comprehensive analysis of the Citi Bike program in New York City, spanning from April 2023 to March 2024. Through data visualization and interpretation, the analysis seeks to uncover key insights into bike usage patterns, popular routes and seasonal variations. These insights will enable stakeholders to make informed decisions regarding resource allocation, infrastructure development, and marketing strategies to enhance the overall efficiency and effectiveness of the Citi Bike program.

- View Tableau Dashboard website here: https://vanillatyy1.github.io/18_Citibike/

- View the project on the actual Tableau website: [here](https://public.tableau.com/shared/KJB9H49HY?:display_count=n&:origin=viz_share_link)
 

## About the Dataset 
Citi Bike stands as the nation's largest bikeshare program, boasting 25,000 bikes and a network of over 1,500 stations spanning Manhattan, Brooklyn, Queens, the Bronx, Jersey City, and Hoboken. Offering the convenience of unlocking bikes from one station and returning them to any other within the system, Citi Bike facilitates seamless urban transportation.

Since its inception in 2013, the Citi Bike program has established a robust infrastructure for data collection, meticulously gathering information on program utilization. Monthly, comprehensive bike data is compiled, organized, and made publicly accessible through the Citi Bike DataLinks portal at https://citibikenyc.com/system-data.

This report explores the monthly data specific to Jersey City, covering the period from April 2023 to March 2024. Its objective is to offer insights into ridership growth, identify the most popular starting and ending locations for journeys, and analyze peak usage hours during both summer and winter months.

## Observation About the Dataset
During the creation of the map visualization, I noticed a discrepancy where multiple latitude and longitude values were linked to the same station ID.

Additionally, some of the coordinates were plotting stations in the middle of the water. To address this, I attempted to refine the dataset by creating a master dataframe with only unique station names and IDs. I calculated the average latitude and longitude coordinates, rounding them down to six decimals, in an effort to display one dot per station ID on the map. However, upon reviewing the resulting dataframe, I found that at least 112 values had latitude and/or longitude coordinates with less than six decimals. Further investigation revealed that some station IDs in the original file did not have six decimal places to begin with.

To overcome these challenges, I decided to take a different approach. I exported the concatenated dataset with dropped NA values and loaded it into Tableau. I drew average coordinates without rounding down and filtered out stations with significantly fewer riders, focusing on the top 10 stations. To ensure accurate mapping, I intend to manually search for the proper latitude and longitude coordinates that match the stations using Google Maps or another advanced method. However, due to time constraints, this step will be a project for the future.

Additionally, I noticed that there are multiple ride IDs where the start station is the same as the end station. This suggests that riders may be testing out bikes or completing round trips. While this is understandable from a privacy perspective, as the dataset contains unique ride IDs, it does not provide insight into demographic data or whether multiple ride IDs belong to the same member or person.

**Meet the Bikes**
   ![Meet the Bikes](https://github.com/vanillatyy1/18_Citibike/blob/a4abca009e4e33abb73b48f09a37e435a5226400/Images/meet_the_bikes_sc.jpg)

### Total Number of Rides per Month:
- There is a general increasing trend in the total number of rides per month from April 2023 to August 2023
- The number of rides reached its peak in July 2023 with 111,701 rides and then decreased until January 2024
- However, there is a noticeable decline in the total number of rides in the first three months of 2024 compared to the previous months in 2023

**Number of Rides**
   ![Number of Rides](https://github.com/vanillatyy1/18_Citibike/blob/a4abca009e4e33abb73b48f09a37e435a5226400/Images/no_of_rides_sh_sc.jpg)

## Number of Rides by Membership:
- The number of rides by members with membership plans follows a similar pattern to the total number of rides per month, showing an increasing trend from April 2023 to August 2023, followed by a decline. It then resumes an increasing trend starting in February 2024
- There is a decrease in the number of rides by members from December 2023 to March 2024, suggesting a potential decline in membership activity during these months

## Number of Rides by Casual Riders:
- The number of rides by casual riders (e.g., visitors with day passes or single ride purchases) also exhibits a similar trend to the total number of rides per month, increasing from April 2023 to July 2023, then gradually decreasing during the winter months. It picks up again with increased activity starting February 2024

**Number of Rides by Membership**
   ![Number of Rides by Membership](https://github.com/vanillatyy1/18_Citibike/blob/a4abca009e4e33abb73b48f09a37e435a5226400/Images/no_of_rides_membership_sc.jpg)

## Number of Rides by Rideable Type

### Classic Bike:

- The number of rides on classic bikes displays a consistent increase from April 2023, peaked in August 2023 and gradually declined thereafter, hitting a low point in January 2024

- This decline contrasts with the increasing popularity of electric bikes over the same period

### Electric Bike:
- Electric bikes show ride numbers steadily decreasing from April 2023 to December 2023
- Rides on electric bikes experienced a notable surge in January 2024, suggests a growing preference for electric bikes among riders, potentially influenced by factors like convenience and environmental awareness

**Number of Rides by Membership Type**
   ![Number of Rides by Membership Type](https://github.com/vanillatyy1/18_Citibike/blob/c023b8b92dc417ff5b679c2acec29ea970936761/Images/no_of_rides_rideabletype.jpg)

## Top Station Popularity By Season 

### Spring:
In spring, Grove St PATH emerges as the top starting station, followed closely by Hoboken Terminal - River St & Hudson Pl, then by South Waterfront Walkway - Sinatra Dr & 1 St.
The top ending stations in spring feature Hoboken Terminal - River St & Hudson Pl, then by South Waterfront Walkway - Sinatra Dr & 1 St.

### Summer:
Grove St PATH remains the most popular starting station in summer, with an increase in rides compared to spring.
Hoboken Terminal - River St & Hudson Pl maintains its position as the top ending station in summer, followed by South Waterfront Walkway - Sinatra Dr & 1 St.

### Autumn:
In autumn, Hoboken Terminal - River St & Hudson Pl and Grove St PATH continue to dominate as the top starting stations.
The top ending stations in autumn includes a mix of familiar locations, with Hoboken Terminal - Hudson St & Hudston Pl leading the ranks.

### Winter:
Winter sees a slight shift in popularity, with Hoboken Terminal - River St & Hudson Pl and Grove St PATH still leading as the top starting stations.
The top ending stations in winter exhibit similar trends to the starting stations, with Hoboken Terminal - River St & Hudson Pl and Hoboken Terminal - Hudson St & Hudston Pl maintaining their positions.

**Starting Station Popularity**
   ![Starting Station Popularity](https://github.com/vanillatyy1/18_Citibike/blob/a4abca009e4e33abb73b48f09a37e435a5226400/Images/starting_station_pop_sc.jpg)

**Ending Station Popularity**
   ![Ending Station Popularity](https://github.com/vanillatyy1/18_Citibike/blob/a4abca009e4e33abb73b48f09a37e435a5226400/Images/ending_station_pop_sc.jpg)


## Heatmap

### 1. Seasonal Variation in Ridership:
- Ridership shows variation across different seasons. For instance, during spring and summer, ridership tends to peak during the evening hours (5pm to 7pm), while in autumn and winter, the peak hours shift slightly earlier, from 5pm to 6pm.

### 2. Weekday vs. Weekend Patterns
- Weekday mornings (6am to 8am) consistently show higher ridership compared to weekends during the same time period. This suggests that bike usage during these hours might be primarily for commuting purposes.
- On weekends, ridership tends to peak during mid-morning hours (7am to 8am) rather than during the typical morning rush hours seen on weekdays.

### 3. Peak Hours
- Across all seasons, the peak hours for ridership are consistently observed during weekday evenings, particularly between 5pm and 7pm. This indicates that many riders use bikes for their commute back home after work.

**Heatmap by Season/ Hour of Day**
   ![Heatmap by Season/ Hour of Day](https://github.com/vanillatyy1/18_Citibike/blob/a4abca009e4e33abb73b48f09a37e435a5226400/Images/heatmap_sh_sc.jpg)

### 4. Casual vs. Member Ridership
- Member riders consistently contribute to a higher proportion of overall ridership compared to casual riders, indicating that the bike-sharing program has a significant base of regular users.

### 5. Seasonal Trends
- Summer and spring exhibit higher overall ridership compared to autumn and winter, which is expected due to more favorable weather conditions during these seasons.

**Heatmap by Membership Type**
   ![Heatmap by Membership Type](https://github.com/vanillatyy1/18_Citibike/blob/a4abca009e4e33abb73b48f09a37e435a5226400/Images/heatmap_by_membershiptype_sc.jpg)

## Conclusion:

In conclusion, the analysis of Citi Bike data has provided valuable insights into ridership patterns, seasonal trends, and user behavior. By examining factors such as hour of the day, weekday usage, and seasonal variations, we've gained a deeper understanding of how riders interact with the bikeshare program across different contexts. These insights can inform strategic decision-making processes aimed at optimizing service efficiency, enhancing user experience, and promoting sustainable urban transportation solutions. 

As cities continue to evolve, leveraging data-driven approaches like this will be crucial in shaping the future of urban mobility.
