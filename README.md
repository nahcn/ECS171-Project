# Incarceration by State

## ECS 171 Spring 2021 Project

## Group Members

### Software Engineering

- Tarun Nagineni
- Tyler Pickles
- Andrew Marquez

### Data Management

- Nicholas Chan
- Kyle Li

### UI/UX

- Harrod Tang
- Chethana Kandula

### Machine Learning and Algorithms

- Frances Quynn
- Gharam Alsaedi

### Quality Assurance

- Christina Determan
- Mihir Lele

### Management

- Daniel de la Calle

## Project Goal

Measure trends in crime, incarceration, and poverty rate by state

## Repository Overview

`datasets`: Contains the data sets analyzed

`data_management_and_models`: Contains a notebook file with the code for data
processing and model exploration

`Voila`: Contains a notebook file which can be viewed as a web-based front-end
using the `Voila` package


## KMeans Clustering Algorithm and Boxplot

For the second model, we clustered the data with the KMeans algorithm according to the number of states to compare attributes between the states. The first part of the K-means section of Voila provides box plots that were formed to group states along particular thresholds for each feature in groups of low, medium, and high, in respect to the particular feature being measured. For example, when grouping the states by population, California and Texas have the highest population. California and Texas were also in the highest group for prisoner_count. We also see that the states Florida and New York were in the medium category for both state_population and prisoner_count. States put in the lowest category for state_population were also in the lowest category for prisoner_population. This result confirms what we already might imagine, that states with more people,and more populationally dense areas such as California, would therefore have more people committing crime and facing incarceration.

For KMeans clustering, we relabeled the states column using LabelEncoding, so that we could label each of the points on the scatterplot. Additionally, categorizing the data by year allowed us to focus on one sample for each state, so we could tell which states belonged to which cluster/ color. It also allowed us to analyze the data across years from 2001 to 2015. It didn’t make sense to evaluate the accuracy of the KMeans algorithm, since for this algorithm, the accuracy would converge to 1.0 as k increased, since increasing the number of clusters would potentially perfectly fit the algorithm to each individual data point. We felt this algorithm would be the most effective in understanding our data, since we could see how states were grouped, but also since we noticed that certain trends between features we thought would exist did not. For example, in the correlation matrix, we noticed a negligible correlation between poverty_rate and prisoner_count. We also noticed a negative correlation between poverty_rate and violent_crime_total. We would think that these pairs of features would be positively correlated since higher poverty_rate might indicate higher crime and violence, which would lead to more incarcerations and higher prisoner_count. However, the contradictory results indicate that there is need for further research as to why states with more poverty might not mean higher incarceration. A possible explanation is that states with high poverty may have lack of funding for law enforcement and thus fewer arrests, or simply there are fewer affluent areas in those states, thus less incentive for break-ins. Although violent_crime_total is positively correlated with burglary, the fact that poverty does not indicate that there will be more violence or burglary was an interesting finding, and necessitates more research on what factors do indicate violence and burglary. This finding also shows the need for data analysis to correct preconceived ideas that can perpetuate biases and stereotypes of poorer communities. 

Since a lot of the expected positive correlations between features were not apparent, we thought using an algorithm that would compare data points and group them together seemed like a strong method. That way when using KMeans in three dimensions, we could see how certain combinations of features compared across states. Although KMeans did reinforce the positive correlations found in the correlation matrix, it mainly served as a method to visualize the distribution of states across certain features. For example, when comparing burglary, violent_crime_total, and prisoner_count, it can be seen that states with low burglary rate were found in the low violent_crime_total and low prisoner_count clusters, for which, as we can see in the correlation matrix, all values do, in fact, have high correlation values. 

In the plots below, we can compare how state_population, prisoner_count, violent_crime_total, and burglary have changed over time for each state for years 2001 vs. 2015, where k=3. In 2001, the state with the highest population, represented by the data point 4, was California. In 2015, we see that Texas and New York have increased in population and are grouped in the high population cluster. We can also tell that the populations of states have changed significantly between 2001 and 2015, since a large portion of states initially in the low cluster are grouped in the medium cluster in the state_population vs. jurisdiction K-means plot for 2015. We also see that Florida also changed to the high cluster for state population.


 Guide to tell which numbers reference each state. 
 
# 0- Alabama
# 1- Alaska
# 2- Arizona
# 3- Arkansas
# 4- California
# 5- Colorado
# 6- Connecticut
# 7- Delaware
# 8- Florida
# 9- Georgia
# 10- Hawaii
# 11- Idaho
# 12- Illinois
# 13- Indiana
# 14- Iowa
# 15- Kansas
# 16- Kentucky
# 17- Louisiana
# 18- Maine
# 19- Maryland
# 20- Massachusetts
# 21- Michigan
# 22- Minnesota
# 23- Mississippi
# 24- Missouri
# 25- Montana
# 26- Nebraska
# 27- Nevada
# 28- New Hampshire
# 29- New Jersey
# 30- New Mexico
# 31- New York
# 32- North Carolina
# 33- North Dakota
# 34- Ohio
# 35- Oklahoma
# 36- Oregon
# 37- Pennsylvania
# 38- Rhode Island
# 39- South Carolina
# 40- South Dakota
# 41- Tennessee
# 42- Texas
# 43- Utah
# 44- Vermont
# 45- Virginia
# 46- Washington
# 47- West Virginia
# 48- Wisconsin
# 49- Wyoming

Results:

2001 vs. 2015:


For both 2001 and 2015, states with higher populations also had higher prisoner_count. And the state of Florida that was added to the high state_population cluster in 2015, was also added to the high prisoner_count cluster in 2015. 


For violent_crime_total, we notice little change in the states in each cluster between 2001 and 2014, which verifies the small correlation between violent_crime_total and state_population found in the correlation matrix, since we know the population of states increased between 2001 and 2015.


In the correlation matrix, there is an even smaller correlation between burglary and state_population, given the clusters between 2001 and 2015 did not change much.



Comparing clusters for prisoner_count and burglary for 2001 and 2015, we can see that the positive correlation between these two features remains consistent. States with higher burglary rates were in the cluster of higher prisoner count and states with lower burglary rates were in the lower burglary rate cluster.


Lastly, looking at a 3D K-means cluster, we see that consistent across 2001 and 2015, states with lower burglary had less violent crime and less prisoner population, and states with high burglary rates had high violent crime rates and higher prisoner population. Although the correlation between poverty_rate and burglary, and poverty_rate and violent_crime was not as we expected, the correlation between violent_crime, burglary, and prisoner_count was. So, states with more poverty does not mean there is more incarceration. To understand better how poverty affects incarceration rate, it would be interesting to do a focused data analysis of states with both extreme poverty and extreme wealth and look at their crime rate and prisoner_count compared to states that have more of a working class population.

