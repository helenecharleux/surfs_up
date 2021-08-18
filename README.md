# Surf and shakes prokect in Hawai

## 1. Overview of the project

I am passionate about surf and I have just spent amazing time in Hawai playing in the waves. I have a project of living there and opening a surf and shake store. In addition of the surf store, I would like to serve icecreams to locals, tourists and surf riders. I am already working with an investor, W. Avy. He is interested in my project. However he would like to confirm that the weather in Oahu is relevent in order to support this project.

I have already run analytics on the weather dataset W. Avy gave me to analyze the yearly temperatures and precipitations on the island. In spite of that, he wants more information about temperature trends, specifically for the months of June and December. M. Avy is confident about the project. However he wants to be certain that the surf and ice cream shop business is sustainable all year-round.

## 2. Analysis of the results

### 2.1 Optimal overall temperatures in June and December
The average temperature in Oahu for the months of June and December are around 72 degrees Farenheit, repsectively 74,94 Farenheit in June and 71 Farenheit in December. It is optimal temperatures to practice sports and enjoy your time on the beach. However, we have to deeper our analysis to confirm that the weather conditions are optimal to support our business in ice cream.

### 2.2 Most desirable temperatures in June
Thanks to the weather dataset provided by W. Avy, we were able to go futher in our analysis for the month of June. The table below is a summary of the main weather data recorded by the stations on the island.

![June_temps](https://user-images.githubusercontent.com/85641189/129953679-356c752c-0e09-4719-8d85-b3ed81e285a5.png)

The June temperatures have a minimum of 64 Farenheit and a maximum of 85 Farenheit. The data are spread out around the average temperature with a standar deviation of 3,25. 
Our overall analysis for the month of June is that the weather is perfect to practice sports and the temperatures are high enough to support the ice cream business. 

### 2.3 Cooler temperatures during the month of December

The month of December registers cooler temperatures with a minimum of 56 Farenheit and a maximum of 83 Farenheit. The standard deviation is higher than in June, meaning that the temperatures are even more spread around the average temperature of 71 Farenheit.

![Dec_temps](https://user-images.githubusercontent.com/85641189/129958703-66147330-9d7e-4c3a-994c-e0ba37564644.png)

## 3. Further analysis to confirm the investment opportunity

The purpose of my project is to target a wide range of customers, from the surf riders to the local and tourists visiting the island and its beaches. For the moment, we have focused our analysis on the temperatures. We are able to confirm that the temperatures are warm enough to support the ice cream business, specially in June. 

However, highlighting that the temperatures are not so high, we want to go further in the analysis doing some analytics on the precipitations data. We will run two queries identical to the one we used on the temperatures in order to analyze the precipitations in June and December. Our objective is to check that the cool temperatures in June and specifically in December are not related to a high precipitation rate.

The following query will calculate the basics statistics for June.
```
# 10. Write a query that filters the Measurement table to retrieve the precipitations for the month of June. 
june_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) ==6).all()
june_prcp = list(np.ravel(june_prcp))
june_prcp = pd.DataFrame(june_prcp, columns = ['Precipitations'])
june_prcp.describe()
```
The following query will calculate the basics statistics for December.
```
# 11. Write a query that filters the Measurement table to retrieve the precipitations for the month of December. 
dec_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) ==12).all()
dec_prcp = list(np.ravel(dec_prcp))
dec_prcp = pd.DataFrame(dec_prcp, columns = ['Precipitations'])
dec_prcp.describe()
```

## 4. Conclusion: a relevant business project on the island of Oahu

After running our queries on the precipitations for the months of June and December, we are able to  confirm that the weather conditions on the island of Oahu are optimal for our project. The last queries verify that the cool temperatures specifically in December are not related to high precipitation rates. With a year-round sunny weather, we are positive on the relevance of our project.
