# PyBer_Analysis
## Overview
### Project Goals
In this analysis, we sought to derive information on the drivers and fares for each city type. Our first goal was to create a Pandas dataframe which outlined these data points. Second, we were asked to create a multiple line plot that showed the weekely fares for each type of city. This analysis will allow PyBer to have greater insight in to the the distribution of its rideshare business. 

## Results
## Summary Dataframe
Our first goal was to deliver a dateframe which summarized information about drivers, city types and fares. The resulting dataframe is displayed below:

![Summary Dataframe](/analysis/pyber_summary_df.png)

As shown in the dataframe, Urban cities had the highest amount of total rides and total drivers, followed by Suburban and then Rural cities. Urban cities also had the highest amount of total fares, followed by Suburban and Rural cities. 

Rural cities had the highest amount of average fare per ride and average fare per driver, followed by Suburban and then Urban cities. This is likely because Rural rides covered longer distances on average than the rides in Urban and Suburban cities. 

## Total Weekly Fares per City Type
Our second goal was to create a chart which showed the total weekly fares for each type of city. To achieve this goal, we created a multiple line chart so that we could compare the data from all three city types at once. 

For this chart, we first created a dataframe which showed the sum of the fares for each date, and where the indices were the city type and date. We then reset the standard numerical indices. Next, we created a pivot table where the 'date' series became the index, the columns became the city 'type' and the vales were amounts from the 'fare' series. Then, we used the 'df_pivot.loc[]' method to select the rides between the dates of January 1, 2019 and April 29, 2019. A screenshot of this line of code and the resulting dataframe is shown below:

![Loc DF](/analysis/loc_df.png)

Next, we ensured our 'date' index was in datetime datatype. Then, we created a new dataframe using the 'resample()' function to get the sum of the fares for each week in our chosen time period. The code and resulting dataframe are shown below: 

![Resample Dataframe](/analysis/resample_df.png)

Finally, we used the object oriented interface method to plot the dataframe using the df.plot() function. We used the 'fivethirtyeight' graph style for our graph. The final result is shown below:

![Line Chart](/analysis/PyBer_fare_summary.png)

The chart clearly shows that for the chosen time period, Urban cities had the highest total fares, followed by Suburban and then Rural. There are some correlated peaks and dips between the city types, but other changes in total fares in certain city types do not seem to be correlated to the other city types at all. 

## Summary
Here are a few recommendations for addressing disparaties between the city types: 
1. Increase Rural Drivers
There were much less rides in Rural cities than in Suburban and Urban cities. This is almost certainly due in part to a lower demand for rides in less populated areas. However, it could also be partially due to the fact that there are many less drivers in Rural areas. If the amount of drivers in Rural areas is increased, this could increase the total number of rides. This would be beneficial for the company, because Rural rides have the highest average fare. 
2. Increase Rates for Urban Rides
Although the number of Urban rides far surpassed the other city types, the average fare per ride was the lowest in Urban cities. Presumably, the demand for rides in Urban cities is high becuase of the high population. An increase in the fare for these Urban rides could potentially lead to much higher average fares per ride, and could have a negligible impact on the amount of rides that are taken. It would be beneficial to test these Urban rides out at different price points. 
3. Decrease the Rates for Rural Rides
Rural rideers could be deterred from using PyBer because the average fair per ride is so high. Lowering this rate could increase the demand for rides in Rural cities. Although Rural rides are likely longer in distance, they could be shorter in time than Urban and Suburban rides because there is less traffic and congestion in Rural areas. This could justify a price drop in Rural rides, which could increase the amount of rides taken. 