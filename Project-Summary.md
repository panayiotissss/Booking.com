

The data cleaning process begins by removing unnecessary columns from the data set. 
Firstly a check for missing values was performed and shown that there are 23 missing values, which were dealt with by imputing missing values for the ReviewsCount and Rating variables using the mean values. Also some  observations were removed since they were not missing at random.

![Alt text](https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Missing%20values.PNG)


Moving on, box plots of the ReviewsCount, Rating, and Price variables were created  to  visually identify outliers.  Then also the Tukey's method was used to identify outliers for each variable, which were finally chosen to be removed from the dataset so they do not influence the analysis further.

![Alt text](https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Price.png)
![Alt text](https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Rating.png)
![Alt text](https://github.com/panayiotissss/Booking.com/blob/c78a68afa5b9657b964179e839bd0fdc6feecb4a/vizualizations/Reviewscount.png)
