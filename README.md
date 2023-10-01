# Midterm Project- Montesinho Natural Park Wildfire Analysis

## Background/Introduction

Forest fires play an essential role in maintaining the health of a forest by recycling nutrients back into the soil and promoting new growth. However, climate change and deforestation have lead to an increase of wildfires. Coupled with the negative effects of wildfire air pollution and increased greenhouse gas emissions, it is becoming imperative to reduce the risk of forest fires. As a result, actionable steps to prevent and suppress forest fires and manage post fire damage are being taken. Conducting danger assessments of forest fires will help determine where to allocate resources and can help in mitigating wildfire damage. 

Forest fire data from Montesinho Natural Park, Portugal was selected for this project. The dataset covers 517 forest fires that occured between January 2000 to December 2003.

# Forest Fire Indexes

The danger rating of a wildfire is measured by the Fire Weather Index (FWI) system. The Fire Weather Index (FWI) is composed of 6 components that describe fuel moisture and weather conditions. These components account for fire behaviour. The fuel moisture codes are numeric ratings that describe the moisture content of the forest floor and dead organic matter. The higher the value, the lower the moisture content. Each fuel moisture code accounts for different layers of the forest floor in the following order: 

 1- Fine Fuel Moisture Code (FFMC): (Top Layer) A numeric rating of surface level fuel moisture, taking into account loose non-living organic debris, leaves, bark, twigs, flowers, fruits, and other vegetable matter. <br>
 2 -Duff Moisture Code (DMC): (Middle Layer)  A numeric rating of the fuel moisture of decomposed organic material beneath the surface level. <br>
 3- Drought Code (DC): (Deep Layer) A numeric rating of the fuel moisture of deep, compact organic layers. 

The remaining 3 components help describe the behaviour of a fire. As the fire danger increases, these components also increase. 

 4 - Initial Spread Index (ISI): Numeric rating of the expected rate of fire spread derived from Fine Fuel Moisture Code (FFMC) and wind speed. <br> 
 5 - Build Up Index (BUI): Numeric rating of the total amount of available combustible fuel. This is calculated by adding the Duff Moisture Code (DMC) and Drought Code (DC). <br> 
 6 - Fire Weather Index (FWI): Numeric rating of fire intensity. Derived from Initial Spread Index (ISI) and Build Up Index (BUI). 


## Project/Goals
 * Can we find any variables within the data to predict consequential properties of fires like size, danger and frequency?
 * Which fire indexes provides the greatest indicator to assess for the total area burned by a fire and initial spread index (ISI)?
 * Create a model to predict the Initial Spread Index (ISI) of a fire 

## Process
Forest fire analysis was performed using forest fire data from Montesinho Natural Park, Portugal:
* Data Cleaning
    * Duplicated values, null values, and outliers were removed.
* Exploratory Data Analysis & Visualization
    * Correlations between fire indexes were explored.
    * Analysis of variables against Initial Spread Index (ISI) and area burned were performed. 
* Data Modelling
    * Drought Code (DC) and month number were used to predict Initial Spread Index (ISI) value.

## Results

* Fine Fuel Moisture Code (FFMC) was skewed towards its theoretical of 99, which implies that a high Fine Fuel Moisture Code (FFMC) is either a precondition for a fire of any size, or that high Fine Fuel Moisture Code (FFMC) is a common property of the local climate, regardless  of fire risk. 
* Highest number of fires were in August and September. The smallest number of fires was in November. 
* The likelihood for a fire to spread is higher in August and September compared to March
* The average (Initial Spread Index) ISI per season followed a seasonal pattern. The Initial Spread Inded (ISI) was highest during summer with the highest temperatures, slightly decreases in Fall and is the lowest in the Winter. By Spring, the Initial Spread Index (ISI) increases as the temperature increases.
* Seasons containing higher average wildfire Initial Spread Indexes (ISI) had an increased number of high and extreme danger fires. These fires are important to note because they are difficult to control. 
* The average Drought Code (DC) also followed the same seasonal pattern as Initial Spread Index (ISI). The Drought Code (DC) was found highest in August and September (Summer) and lowest during the winter (December). 
* If we can predict the Initial Spread Index (ISI) using the drought code (DC) in a given month, this may help assess the danger of a fire becoming uncontrollable. 

# The Model
A multilinear regression was made to help model the data from Montesinho Natural Park wildfires. 

The final model was found to be: 
* ISI = (-0.000428 * DC) + (1.167389 * month number) 
This model was able to explain 78% of the variance of ISI using DC and month number as the x variables. 

## Challenges 
* The data set did not include important fire parameters such as FWI (Fire Weather Index) and BUI (Build Up Index) which provide the risk rating of a wildfire.
* Data pertaining to the area burned was highly skewed towards 0. This may be because the area was in hectares and that the area burned by the fire was minimal/small and did not spread.
* Number of fires represented in colder months such as November, December and January was small compared to the dataset. May not be an accurate reflection of fires that occur during that month. 
* Data provided the month but not the year. Difficult to ascertain whether or not a yearly trend was present.
* The fire weather indexes for days without fires was not included in the dataset. This reduced the ability to find causality between indexes and fires

## Future Goals
* Other parameters such as rain and temperature could be included in the analysis. An outside datasource with the average rain and temperature for the Montesinho Natural Park can be obtained for comparison.
* The average fire indexes for days without fires can be compared to days with fires. 
* Indexes such as FWI (Fire Weather Index) and BUI (Build Up Index) could be included as they provide a better indication of the risk rating of a wildfire. 
* Further analysis could be done to find the probability of a fire in the Montesinho Natural Park on a given day using the month/day of week.
* Machine learning could be used in the model building process to improve the model. 

