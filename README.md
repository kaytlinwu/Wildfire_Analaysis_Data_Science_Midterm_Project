# Midterm Project- Montesinho Natural Park Wildfire Analysis

## Background/Introduction

Forest fires play an essential role in maintaining the health of a forest by recycling nutrients back into the soil and promoting new growth. However, climate change and deforestation have lead to an increase of wildfires. Coupled with the negative effects of wildfire air pollution and increased greenhoue gas emissions, it is becoming imperative to reduce the risk of forest fires. As a result, actionable steps to prevent and suppress forest fires and manage post fire damage are being taken. Conducting danger assessments of forest fires will help determine where to allocate resources and can help in mitigating wildfire damage. 

Forest fire data from Montesinho Natural Park, Portugal was selected for this Project. The dataset covers 516 forest fires that occured between January 2000 to December 2003.

# Forest Fire Indexes

The Fire Weather Index is a system with 6 components that describe fuel moisture and weather conditions. These components account for fire behaviour. The fuel moisture codes are numeric ratings that describe the moisture content of the forest floor and dead organic matter. The higher the value, the lower the moisture content. Each fuel moisture code accounts for different layers of the forest floor in the following order: 

 1- Fine Fuel Moisture Code (FFMC): (Top Layer) A numeric rating of surface level fuel moisture, taking into account loose non-living organic debris, leaves, bark, twigs, flowers, fruits, and other vegetable matter.
 2 -Duff Moisture Code (DMC): (Middle Layer)  A numeric rating of the fuel moisture of decomposed organic material beneath the surface level. 
 3- Drought Code (DC): (Deep Layer) A numeric rating of the fuel moisture of deep, compact organic layers. 

The remaining 3 components help describe the behaviour a fire. As the fire danger increases, these components also increase. 

 4 - Initial Spread Index (ISI): Numeric rating of the expected rate of fire spread derived from Fine Fuel Moisture Code (FFMC) and wind speed. 
 5 - Build Up Index (BUI): Numeric rating of the total amount of available combustable fuel. This is calculated by adding the Duff Moisture Code (DMC) and Drought Code (DC). 
 6 - Fire Weather Index (FWI): Numeric rating of fire intensity. Derived from Initial Spreed Index (ISI) and Build Up Index (BUI). 


## Project/Goals

 * Which fire indexes provides the greatest indicator to assess for the total area burned by a fire and ISI (initial spread index)?
 * Create a model predict the ISI (Initial Spread Index) of a fire. 

## Process
Forest fire analysis was perfromed using forest fire data from Montesinho Natural Park, Portugal:
* Data Cleaning
    * Duplicated values, null values, and outliers were removed.
* Exploratory Data Analysis & Visualization
    * Correlations between fire indexes were explored.
* Data Modelling
    * DC and month number were used to predict ISI value.

## Results

* The average ISI per season followed a seasonal pattern. The ISI was highest during summer with the highest temperatures, slightly decreases in Fall and is the lowest in the Winter. By Spring, the ISI increases as the temperature increases.
* Seasons containing higher average wildfire ISI had an increased number of high and extreme danger fires. These fires are important to note because they are difficult to control. 
* Average DC also followed the same seasonal pattern as ISI. DC was found highest in August and September (Summer) and lowest during the winter (December). 

# The Model
A multilinear regression was made to help model the data from Montesinho Natural Park wildfires. 

The final model was found to be: 
* ISI = (-0.000428*DC) + (1.167389*month number) 
This model was able to explain 78% of the variance of ISI using DC and month number as the x variables. 

## Challenges 
The data set did not include important fire parameters such as FWI and BUI which provide the risk rating of a fire.
Data pertaining to the area burned was highly skewed towards 0. This may be because the area was in hectares and that the area burned of the fire was minimal/small and did not spread.
Data provided the month but not the year. Had to tell if there was a trend per year.


## Future Goals

