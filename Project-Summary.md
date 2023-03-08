After the data was donwloaded from kaggle and loaded into R,

The data cleaning process begins by removing unnecessary columns from the data set. 
Firstly a check for missing values was performed and shown that there are 23 missing values, which were dealt with by imputing missing values for the ReviewsCount and Rating variables using the mean values. Also some  observations were removed since they were not missing at random.

![Alt text](https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Missing%20values.PNG)


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
Then two new data frames were  created containing   the major cities and rest of the locations. This step was taken to avoid bias in the analysis caused by small sample sizes in some areas.

Below we can see the visualisations of Major Cities & Rest Locations in terms of Price , Rating and Reviews:

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
