# FlightData



## Dataset

> The data comes originally from RITA where it is described in detail. The dataset consist of flight information for all flights within USA in year 2008. It has 7,009,728 rows of data and 29 features/variables. 


Dataset can be found here: http://stat-computing.org/dataexpo/2009/the-data.html 

## Summary of Findings

> First I found these as issues: 

- No easy way to identify delayed flights; so, I am going to add `Delayed` column to the dataset if the flight is delayed based on DepDelay data as 1 (Yes) or 0 (No) based on x>0 or x<0

- CarrierDelay, WeatherDelay, NASDelay, SecurityDelay, LateAircraftDelay, CancellationCode have both NaN's and 0's, I am going to convert all NaN's to 0's  

- DepDelay has some missing values, looking at it revealed these flights were cancelled. [Do I want to do something here]

- DepTime, CRSDepTime, ArrTime, CRSArrTime are of type float rather than timedate( I have observed this, but I don't think it is required to be changed. However, I have made a mental note to change them if I see it would be better).

Then I found:

* When ArrDelay or DepDelay is bigger or equal to 15 minutes we see data about what caused the delay in the columns of CarrierDelay, WeatherDelay, NASDelay and LateAircraftDelay. The sum of these columns is equal to the DepDelay or ArrDelay.
* When a flight is Cancelled or diverted, we see no data related to cause of the delay.
* December as the worst month to fly with over17 minutes of delay time, and sept/oct as the best months. 
* delay time is considered to be anything =>15 minutes
* I found that cause of delay is highest in this order: LateAirCraft delay, NASDelay, CarrierDelay, WeatherDelay, and Security Delay.

* I found that cancellation delays are in this order: WeatherDelay, CarrierDelay, NASDelay.

* I found that more flights gets delayed than cancelled.
* I found in 2008 what month has the highest delay(dec) based on DepDelay and what month had the lowers (sep/oct)
* I found many of the categorical variables have an impact on the delay and cancellations.
* I found that flights that get diverted have higher delay rates.
* I found some information about the airlines and the percentages of their delay/cancellations.
* I found there are some relations between origin/destination and delay/cancellation.

* I found that the later it is in a day, the higher the chance of delay is.

* I found carriers behave differently depends on what day of the week they fly.


To sum this up at each exploration phase of univariate, bivariate, and multivariate:

** Univariate exploration major finding:

One interesting finding was that the delayed variable demonstrated a very high delayed flight rate without further investigating the data and also ready about what is measured as `delayed`. Further investigation of the data provided me with a range to work with from -10 to 15+. Adjusting based on these numbers, showed a delay rate of almost 19% in year 2008 which seemed to be more reasonable. For the Cancelled variable, only 1% of flights are cancelled, and that seems to be a normal range so no further digging was done here.


** Bivariate exploration major finding:

Many of the categorical features showed a relationship with the delay/cancellation variables. The ones I worked with was unique carrier, origin, destination, day of week, and diverted.


As an example Friday's and later PM flights tend to have higher delay rates. Also some carriers, origins or destinations tend to have more delay rates than others. 

** Multivariate exploration main finding:
Delay rates for flights based on the day of the week, and the carrier type varies for some and only stays the same for a minority. For example carrier AQ seems to be constant throughout the week, while HA carrier demonstrates a close to 10% delay on Fridays, and 25% delay rate on Mondays.




## Key Insights for Presentation

> Select one or two main threads from your exploration to polish up for your presentation. Note any changes in design from your exploration step here.

In the presentation, my focus was what my features of interest(delaying and cancelling flights) are related to or could be affected by. 

I overview the following git prior to starting the project:

https://shawnemhe.github.io/udacity-data-analyst/p6/python_eda/python_eda.html


Note to the tutor: I thought the practice of slides are pretty cool, but the template was limited in terms of only show casing 3 visualization. So, I picked from each exploration part only one I decided to show. I assume, this is just a practice to learn how to show case your work? 
