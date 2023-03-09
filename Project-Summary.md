**EXPLARATORY ANALYSIS**

After the data was donwloaded from kaggle and loaded into R,

The data cleaning process begins by removing unnecessary columns from the data set. 
Firstly a check for missing values was performed and shown that there are 23 missing values, which were dealt with by imputing missing values for the ReviewsCount and Rating variables using the mean values. Also some  observations were removed since they were not missing at random.



| Name | Place | Type | ReviewsCount | Rating | City | Price Euros |
|------|-------|------|--------------|--------|------|-------------|
| 0 | 0 | 0 | 13 | 10 | 0 | 0 |


Moving on, box plots of the ReviewsCount, Rating, and Price variables were created  to  visually identify outliers.  Then also the Tukey's method was used to identify outliers for each variable, which were finally chosen to be removed from the dataset so they do not influence the analysis further.



<table>
  <tr>
    <td>
      <img src="https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Price.png" alt="Price" width="400"/>
    </td>
    <td>
      <img src="https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Rating.png" alt="Rating" width="400"/>
    </td>
    <td>
      <img src="https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Reviewscount.png" alt="Reviews Count" width="400"/>
    </td>
  </tr>
</table>



The data was then grouped by city and the average price, rating, and reviews count for each city was calculated
Then two new data frames were  created containing   the major cities and rest of the locations. This step was taken to avoid bias in the analysis caused by small sample sizes in some areas. Overall, this approach helps to ensure that our analysis is fair and unbiased, and provides valuable insights into the differences between major cities and other locations in the dataset.

Below we can see the visualisations of Major Cities & Rest Locations in terms of Price , Rating and Reviews:

Major Cities: 
<table>
  <tr>
    <td>
      <img src= https://github.com/panayiotissss/Booking.com/blob/db2d387eb1fbe6b97c7c2fab22167bc606b898dd/vizualizations/average%20price%20major.png alt="Price" width="400"/>
    </td>
    <td>
      <img src=https://github.com/panayiotissss/Booking.com/blob/db2d387eb1fbe6b97c7c2fab22167bc606b898dd/vizualizations/Ratingmajor.png alt="Rating" width="400"/>
    </td>
    <td>
      <img src=https://github.com/panayiotissss/Booking.com/blob/db2d387eb1fbe6b97c7c2fab22167bc606b898dd/vizualizations/reviews%20major.png alt="Reviews Count" width="400"/>
    </td>
  </tr>
</table>

Rest Locations:

<table>
  <tr>
    <td>
      <img src= https://github.com/panayiotissss/Booking.com/blob/6eec2c135de6d5284276bd0d0d1f59aac6f7dd8b/vizualizations/price%20rest.png alt="Price" width="400"/>
    </td>
    <td>
      <img src=https://github.com/panayiotissss/Booking.com/blob/6eec2c135de6d5284276bd0d0d1f59aac6f7dd8b/vizualizations/rating%20rest.png alt="Rating" width="400"/>
    </td>
    <td>
      <img src=https://github.com/panayiotissss/Booking.com/blob/6eec2c135de6d5284276bd0d0d1f59aac6f7dd8b/vizualizations/Revies%20rest.png alt="Reviews Count" width="400"/>
    </td>
  </tr>
</table>


Major cities: The average price is €125.11, the average rating is 8.5, and the average number of reviews is 570.3.

Rest of the locations: The average price is €129.25, the average rating is 8.29, and the average number of reviews is 492.45.

From these summary statistics, we can see that there are some differences between the major cities and the rest of the locations in terms of price, rating, and reviews. For example, the major cities have a slightly lower average price but a slightly higher average rating and number of reviews compared to the rest of the locations. These insights could be useful in helping us to better understand the characteristics of different types of locations and how they impact consumer behavior.

An interesting obsevation is the higher price for rest of locations , this could be due to the type of accommodation available in the rest of the locations (e.g., luxury villas, high-end resorts), the location (e.g., rural areas with scenic views), or the amenities and services offered (e.g., private pools, spa services).


Next the relationship between the variables in our dataset (Price, Rating, ReviewsCount) was examined using a correlation matrix. Here is the resulting matrix:

|              | ReviewsCount | Rating | Price Euros |
|--------------|--------------|--------|-------------|
| ReviewsCount | 1.000        | -0.147 | -0.149      |
| Rating       | -0.147       | 1.000  | 0.220       |
| Price Euros  | -0.149       | 0.220  | 1.000       |


Individual regressions were then run in order to examine the relationships and get estimates for the coefficients

These regression analyses examine the relationship between price, rating, and reviews count of hotels in a dataset from Booking.com. The first regression shows that there is a significant positive relationship between the price and the rating of hotels. For every one-unit increase in rating, there is a corresponding increase of €16.35 in the price. The second regression reveals that there is a significant negative relationship between the price and the number of reviews a hotel receives. For every one-unit increase in reviews count, there is a decrease of €0.016 in the price. Overall, these results suggest that higher-rated hotels tend to be more expensive, but receive fewer reviews, while lower-rated hotels tend to be less expensive but receive more reviews.

<table>
  <tr>
    <td>
      <img src= https://github.com/panayiotissss/Booking.com/blob/7bfee01cf4cda6eab28da198c58a1c04f8539fe6/vizualizations/rating%20and%20price%20reg.png alt="Price" width="400"/>
    </td>
    <td>
      <img src=https://github.com/panayiotissss/Booking.com/blob/7bfee01cf4cda6eab28da198c58a1c04f8539fe6/vizualizations/revies%20and%20price%20reg.png alt="Rating" width="400"/>
    </td>
    </td>
  </tr>
</table>


Next,  cities were added into the mix by splitting the data into major and minor cities based on a predefined list. We then created linear regression models for each group and found that for the major cities, only rating was a significant predictor of price while for the rest of the locations, both rating and reviews count were significant. We compared the coefficients of the predictor variables between the two models and visualized the data with scatter plots. Overall, this analysis provides insights into the different factors that influence hotel prices in major cities versus minor cities.



<table>
  <tr>
    <td>
      <img src= https://github.com/panayiotissss/Booking.com/blob/790ca78f40927123b2882527e7a0222192304fa1/vizualizations/Major%20cities%20model.png alt="Price" width="400"/>
    </td>
    <td>
      <img src= https://github.com/panayiotissss/Booking.com/blob/790ca78f40927123b2882527e7a0222192304fa1/vizualizations/rest%20of%20locations%20model.png alt="Rating" width="400"/>
    </td>
    </td>
  </tr>
</table>



Next, we performed regressions on individual cities to examine how the relationships between the predictor variables and hotel prices differ by city. W
Overall, this analysis provides insights into how different factors impact hotel prices in different locations. By examining these relationships at a more granular level, we can better understand the factors that contribute to hotel prices in different cities and potentially use this information to make more informed pricing decisions in the future.

In general, a higher rating is associated with a higher price, while the relationship between the number of reviews and the price is less consistent across the different cities. The results can be used to make predictions about the price of accommodation in each city based on their rating and review count.

| City        | Intercept | Rating | ReviewsCount |
|-------------|-----------|--------|--------------|
| Amsterdam   | -194.26   | 39.70  | 0.03        |
| Bemelen     | 238.16    | -0.76  | -0.09       |
| Breda       | -177.82   | 32.63  | 0.02        |
| Delft       | -219.60   | 43.26  | -0.04       |
| Den Bosch   | -107.50   | 29.34  | -0.03       |
| Eindhoven   | -232.65   | 40.19  | -0.02       |
| Groningen   | -197.20   | 35.63  | 0.00        |
| Haarlem     | -313.40   | 52.64  | -0.00       |
| The Hague   | -332.81   | 54.73  | -0.02       |
| Hoofddorp   | -35.56    | 15.40  | 0.02        |
| Leeuwarden  | -80.16    | 22.64  | -0.01       |
| Maastricht  | 405.20    | -21.48 | -0.03       |
| Middelburg  | -9.59     | 14.41  | 0.02        |
| Nijmegen    | 34.25     | 11.02  | -0.01       |
| Roermond    | -119.60   | 27.69  | -0.01       |
| Rotterdam   | -467.89   | 63.01  | 0.04        |
| Scheveningen| 60.12     | 14.46  | -0.03       |
| Utrecht     | -230.80   | 41.17   | 0.01       |
| Valkenburg  | 27.01     | 11.39   | 0.01       |
| Vlissingen  | 23.60     | 13.46   | -0.01      |
| Voorthuizen | 179.71    | -6.24   | 0.00       |
| Zandvoort   | 53.48     | 9.13    | 0.05       |
| Zwolle      | -119.78   | 24.54   | 0.03       |




**Predictive Modeling**

In this section, the cleaned and prepared hotels dataset will be used in order to develop predictive models that can  estimate the price of a hotel as accurately as possible based on its characteristics. The goal is to identify which variables are the most important predictors of hotel price, and to develop models that can be used to inform pricing decisions and improve revenue management. The models will be evaluated based on performance and  will be compared based on their accuracy using a variety of metrics. 




