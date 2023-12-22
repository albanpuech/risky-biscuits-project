
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Two Images Side by Side</title>
  <style>
    .image-container {
      display: flex; /* Use flexbox for layout */
    }

    .image-container img {
      width: 50%; /* Make each image take up 50% of the container width */
      height: auto; /* Maintain the aspect ratio of the images */
    }
  </style>
</head>

# Cheers to Latitude: A Journey Through Climate and Beer Preferences


![image](https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/baneer.png?raw=true)


## 🍻 Introduction


### Beer Reviews

If you live in Switzerland and have ever been to South America, you have probably noticed that people are more outgoing, warmer and approachable there. Well, that’s not just your perception: the climate you live in really does shape your personality. In fact, research shows that if you live in a warmer climate, you tend to have greater social tendencies, emotional stability, extroversion, and openness to new experiences ([Wei et al., 2017](https://www.nature.com/articles/s41562-017-0240-0)). 

If climate makes us different, there is for sure something that we all share: our love for beer. Yes, the amber elixir that brings people together across continents. But, hang on, could there be a mysterious link between the climate that molds our personalities and the way we savor our beers? 

In order to answer this enigmatic question we need data! Luckily, people around the world have been rating beers for a long time on websites like *Beer Advocate* or *Rate Beer*. 

<p align="center">
  <img src="https://cdn.beeradvocate.com/im/meta/beeradvocate-meta-respect-beer-logo.png" width="100" style="margin-right: 100px;"> 
  <img src="https://www.ratebeer.com/images/logos/login-logo.png" width="100">
</p>


From these platforms, we gathered 1.2M reviews from 63K American users evaluating 27K different beers of 104 different types ([dataset](https://drive.google.com/drive/folders/1Wz6D2FM25ydFw_-41I9uTwG9uNsN4TCF)). 
A complete review looks like this:

<p align="center">
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/ex_review.png?raw=true" width="600">
</p>

A review on *Beer Advocate* contains the following information:
- The **name** of the beer.
- The **style** of the beer.
- The **alcohol** by volume.
- The **name** of the breweries and its location.
- The **username** of the author and its location.
- A **rating** indicated in red, that ranges from 1 to 5.
- The relative difference, denoted **rDev**, between the rating given by the user and the average rating of the beer considering all reviews it received.
- A list of 5 scores: **look**, **smell**, **taste**, **feel**, and **overall**.  These also range from 1 to 5. Note that the **rating** is not directly obtained from these, nor is the "overall" related to the other scores.
- The **text** of the review.
- The **date** and **hour** when the review was posted.

We work with all the review features except the **rating** and **rDev** ones as these are not available on *Rate Beer*

### Climate Data

As we are interested in studying the impact of climate on the beer reviews, we have to choose what climate data to use. While many climate classifications exist, we'll be using the popular Köppen climate classification. 

<p align="center">
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/us%20climate.png?raw=true" width="600">
</p>

Let's look at the climates in the US. There are 10 different climates in the US. These are:

| Scheme | Seasonal precipitation                 | Temperature             |
|--------------------------------------|----------------------|------------------|
| **B (Dry)**                               | s (Semi-Arid or steppe) | k (Cold)      |
| **C (Temperate)**                         | f (No dry season)      | a (Hot summer)   |
|                                           | s (Dry summer)    | b (Warm summer)  |
| **D (Continental)**                       | f (No dry season)      | a (Hot summer)   |
|                                           | s (Dry summer)  | b (Warm summer)  |
|                                           |                 | c (Cold summer)  |



Now that we have lots of data, let's dive into it! 🤿

## 🍻 Climate and beers

To explore how climates could impact the appreciation of beer, we first look at the general distribution of each score per climate. We first look at the average "overall" score per climate. We also show the micro-average:

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/overall_climate.png?raw=true" height="300">
</p>

We can also look at the other scores:
<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/climate_average_ratings.png?raw=true" height="300">
</p>



From these plots, we can see that each sub-rating follows the same trends. This means that if there is an influence of climate on the scores, its impact is rather the same across all score categories. This is less the case for the appearance score, which stays rather constant across all climates.

Keeping in mind that the y-axis does not start at zero on these plots, we still observe a difference of around 4 percent in the mean overall score across climates. Indeed, a few climates show very low average scores, while others show very high ones. This is the case of Csa and Dfa. These climates have a hot summer which might make the users more inclined to appreciate beers in general because of the social aspect and their appreciation for a cold drink on a hot summer day. On the other hand, Dsb and Dsc climates give ratings under the averages. Both of these are continental and Dsc has a cold summer. Would it then be the case that people living in colder climates have higher beer expectations and standards?

Looking at the plot of the climate zones in the US, we can see that Dsb and Dsc only cover two states: Idaho and Washington. We can also check the number of reviews per climate:

<p align="center">
  <br>
  <img src="assets\img\Number of ratings per climate.png" height="400">
</p>

It appears that the different climates are imbalanced with respect to the number of reviews. We thus have to group climate zones together if we want to have enough beers in all groups. This is what we are going to explore next!

### Climate factors and beers

In this part, we regroup the climate zones based on their scheme, seasonal precipitation, and summer heat level as specified in the Köppen climate classification as shown in the introduction. 


#TODO : add Number of ratings per scheme...


The means of the different scores are shown in the figures below:




  <div class="image-container">
    <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_scheme.png?raw=true" height="300">
    <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_preci.png?raw=true" height="300">
    <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_temp.png?raw=true" height="300">
  </div>
  <br>



Looking at the first figure on the left, dry climates show smaller average overall, aroma, taste and palate scores than the other climates. However, the appearance scores are much more similar across temperate, continental and dry climates.


<!-- <p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_scheme.png?raw=true" height="600">
</p>
</p> -->

On the second figure, the average scores stay rather constant across climates. The overall score is larger in the dry climates, while the taste, palate, aroma and appearance are larger in climate zones that don't have dry seasons. 




<!-- <p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_preci.png?raw=true" height="600">
</p>

And at the summer temperature:

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_temp.png?raw=true" height="600" > -->



Hot and warm summers show very similar average scores. There is however a much larger difference with cold summer which shows lower scores across all categories. 

### Conclusion on climate and reviews

🍺 First of all, there appears to be a correlation between the climatic conditions and the average ratings. Climate is known to influence personality traits, and it may also influence beer preferences.

🍺 What we have seen is that areas with hot summers also have larger beer scores, which could be because of the social and refreshing aspects of beer consumption in warmer areas. 

🍺 On the other hand, we have also observed that colder climates are associated with lower scores, which may come from the fact that people in colder climates have higher expectations or different standards of beer. This may be because they put more emphasis on the quality or taste of beers. 

🍺 The appearance score was the most stable one across the different climate regions, maybe because it is also the hardest criterion to rate, as opposed to the palate and the taste that may have a larger impact on people's beer appreciation.

## 🍻 Climate and styles of beers 

Having unraveled the preliminary layers of our investigation into the impact of climate trends on beer reviews, we now pivot our analytical lens toward the world of beer types. 

The initial exploration revealed how overall, taste, aroma, appearance, and palate ratings are influenced by climatic conditions. However, understanding the nuanced relationship between climate and beer preference requires a deeper look into the styles of beers. Do users from certain climates have preferences for certain beers?

There exist a lot of beer styles. In our dataset only, there were 104 of them. To have a more meaningful analysis we mapped them to 10 general styles. The ten styles are: Lager, Pale Ale, Blonde Ale, Brown Ale, IPA, Wheat beer, Porter, Stout, Sour Ale, Scottish Ale. Here is a visualization of the style's ranking :

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/styles_beer.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

*Fun fact*: This mapping was performed manually following an article by EHL (https://hospitalityinsights.ehl.edu/beer-types). 👍

First, let's take a look at the overall ratings given to each beer by the respective climates. On this plot, we've added the micro average, i.e. the overall mean over the climates.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/beer_type_average_ratings.png?raw=true" max-height="600" title="Overall beer rankings per beer style as a function of the climate">   
</p>

There are indeed significant variabilities between the overall score of the various beer styles by the different climates, leading us to think that people from certain climates prefer certain beer styles. However, when ranking the best beers per climate group, we could immediately notice that there is very little variability between the climate groups. 

Maybe the variability lies in the climate subgroups. To look into this, we computed the best ranked, i.e. best average overall rating, and the most popular, i.e. most reviewed, beers per climate subgroup. Here are the results :

 

<table style="border-collapse: collapse; border: 2px double black;">
  <tr>
    <td></td>
    <td colspan="3" align="center"><font color="Darksalmon">Scheme</font></td>
    <td colspan="2" align="center"><font color="Tan">Precipitation</font></td>
    <td colspan="3" align="center"><font color="Peru">Temperature</font></td>
  </tr>
  <tr>
    <td><b>Rank</b></td>
    <td><b><font color="Darksalmon">Temperate</font></b></td>
    <td><b><font color="Darksalmon">Continental</font></b></td>
    <td><b><font color="Darksalmon">Dry</font></b></td>
    <td><b><font color="Tan">Without dry season</font></b></td>
    <td><b><font color="Tan">With dry season</font></b></td>
    <td><b><font color="Peru">Hot summer</font></b></td>
    <td><b><font color="Peru">Warm summer</font></b></td>
    <td><b><font color="Peru">Cold summer</font></b></td>

  </tr>
  <tr>
    <td>1st</td>
    <td>Sour Ale</td>
    <td>Sour Ale</td>
    <td>Sour Ale</td>
    <td>Sour Ale</td>
    <td>Sour Ale</td>
    <td>Sour Ale</td>
    <td>Sour Ale</td>
    <td>Sour Ale</td>
  </tr>

  <tr>
    <td>2nd</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
  </tr>

  <tr>
    <td>3nd</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
  </tr>

  <tr>
    <td>4th</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
  </tr>

  <tr>
    <td>5th</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
  </tr>
</table>

 <br><br>

<table style="border-collapse: collapse; border: 2px double black;">
  <tr>
    <td></td>
    <td colspan="3" align="center"><font color="Darksalmon">Scheme</font></td>
    <td colspan="2" align="center"><font color="Tan">Precipitation</font></td>
    <td colspan="3" align="center"><font color="Peru">Temperature</font></td>
  </tr>
  <tr>
    <td><b>Popularity</b></td>
    <td><b><font color="Darksalmon">Temperate</font></b></td>
    <td><b><font color="Darksalmon">Continental</font></b></td>
    <td><b><font color="Darksalmon">Dry</font></b></td>
    <td><b><font color="Tan">Without dry season</font></b></td>
    <td><b><font color="Tan">With dry season</font></b></td>
    <td><b><font color="Peru">Hot summer</font></b></td>
    <td><b><font color="Peru">Warm summer</font></b></td>
    <td><b><font color="Peru">Cold summer</font></b></td>

  </tr>
 

  <tr>
    <td>1st</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
    <td>IPA</td>
  </tr>

  <tr>
    <td>2nd</td>
    <td>Pale Ale</td>
    <td>Pale Ale</td>
    <td>Pale Ale</td>
    <td>Pale Ale</td>
    <td>Pale Ale</td>
    <td>Pale Ale</td>
    <td>Pale Ale</td>
    <td>Pale Ale</td>
  </tr>

  <tr>
    <td>3rd</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
    <td>Brown Ale</td>
  </tr>

  <tr>
    <td>4th</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
    <td>Porter</td>
  </tr>

  <tr>
    <td>5th</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
    <td>Stout</td>
  </tr>
  
</table>

We see that the ranking and popularity are always the same accross climate subgroups. This means that the style of the beers is not what causes the variability in the scores. Something interesting we have learned through this analysis is that the best ranked ranked beer style is not the one that is the most reviewed by americans. The following plot summarizes the highest ranked and most popular styles.


<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/style_ranking_best_beer.png?raw=true" max-height="200" title="Average position of each beer, ranked by overall rating">   
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/style_ranking_popularity.png?raw=true" max-height="200" title="Average position of each beer, ranked by number of reviews">
</p>

In summary, the ratings given to the beer styles between the various climates are significantly different. But, the ratings of the beer styles for the different climate factors are very similar. Therefore, the beer style rankings don't seem to be affected by the climate. This can make us think that there is a different appreciation of the beers in general (ie. higher or lower ratings for all beer styles), but the order of their preference is the same. We therefore need to find a new parameter to investigate that could clarify the difference in ratings given to the various beers.

One of the potential explanation for this is the fact that the chosen general types regroup many different kinds of beers in one. By investigating the beer's features to see if some had a big variation inside of each type, one was coming on top : the alcohol by volume (ABV), as one can see in the following plot.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_styles.png?raw=true" width="800" title="Horizontal boxplot of the ABV per beer style">
</p>

It appears that the ABV varies a lot even inside of each beer style. This could explain why the orders of the beer styles are the same between the climates but the ratings are different. Indeed, the ABV could be a parameter that is more important than the beer style itself. We therefore decided to investigate the ABV and its relation to the ratings given to the beers.

## 🍻 Climate and Alcohol Level of Beers

[A group of researchers](https://dom.pitt.edu/people-drink-more-in-colder-regions-bataller-led-study-finds/) at the University of Pittsburgh found a negative correlation between climate factors and alcohol consumption. This means that, as climate factors like temperature drop, the average alcohol consumption increases. But does this mean that the average drink’s alcohol level rises or rather that people drink more alcoholic drinks in general? Let’s investigate!

### Focusing on ABV per climate

In order to do so, let’s study the ABV rating for each beer and find possible correlations with climate factors. We use the number of rankings given to a beer as a measure of popularity and their overall score as a measure of preference. As for the climate factors, we use the ones described earlier: climate, scheme, seasonal precipitation, and heat level.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_boxplot.png?raw=true" width="200">
</p>

As shown on the boxplot, the rated beers are centered around a mean ABV of 7.0°, and half are contained in the [5.4°, 8.0°] range. We want to know how this distribution differs in the different climate categories. 

First, we compare the popularity and preference of the beers in the different climate conditions based on their ABV. From the grouped climates, we find the three most liked beer styles and the three most reviewed. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_climate.png?raw=true" height="300"> 
</p>

By looking at the two U.S. maps above, we can see that there is a variation in the ABV average between the best beers and the most reviewed beers. It results that the ABV mean of the three favorite beers is higher than the one of the three most popular ones. We can observe a variation across the climates but again, too many climates at a time make the results hard to interpret. We will therefore analyze the three climate levels separately.

It is to be noted that for the three next plots, the ranges of the colorbars are not equal on the left and right plots. This was chosen to better visualize the differences within each plot and because the average ABV of the best beers is always higher than for the most reviewed ones.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_scheme.png?raw=true" height="300"> 
</p>

The resulting plots show a smaller ABV for the users living in a dry climate than for the ones living in temperate or continental climates. This is true for both the best beers and the most reviewed beers. 

This seems counterintuitive as one could think people living in a colder climate drink beers that are lighter and not too alcoholic to create a warming sensation, whereas in a dry climate they drink beers with a higher ABV to provide a sensation of coziness. This is, in fact, not the case here as the only climate we have that is in the dry scheme is the BSk climate which is a cold climate.


<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_precipitation.png?raw=true" height="300"> 
</p>

For the seasonal precipitation groups, the best beers have a higher ABV in locations without a dry season than in those with. In contrast, we can notice that, for the most reviewed beers, there is an increase in ABV for regions with dry seasons, but the difference is not as big as for the best beers.

One could assume that beers with less alcohol are more appreciated in dry season because they are more refreshing. However, this is not true for the most reviewed beers. 

These results could be mitigated by some confounders, mostly one can notice that the separation is East-West and there are way more reviews on the East Coast than on the West Coast. This could be due to the fact that the East Coast is more populated than the West Coast. Therefore, we cannot conclude that the climate is the only factor that influences the ABV of the beers.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_temperature.png?raw=true" height="300"> 
</p>

Lastly, when observing the temperature of summer, the ABV consumed is higher in regions with a hot summer than in those with a cold summer. This is true for both the best beers and the most reviewed beers. The variation is also the biggest among the different climate categories.



### Analysis of ABV

In all cases, we can notice that there is a small difference in ABV means. The typical difference is around 0.1° and the highest variation for one chosen climate category is when we compare hot and cold summer. 

The first main result we find is that U.S. citizens prefer beers with higher ABV compared to the most consumed beers. This is true for all climate categories. Indeed, in the case of the best beers, their average ABV was always above the global mean of 7°.

Then, we find that the ABV is higher in regions with a hot summer than in those with a cold summer. This is true for both the best beers and the most reviewed beers. This could seem to be in contradiction with the conclusions of the study by the University of Pittsburgh. However, we have to keep in mind that we are not studying alcohol consumption but rather the alcohol level of the beers. Therefore, this could mean that people living in colder climates drink more beers but with a lower ABV.

# Conclusion

In conclusion, our exploration of the influence of climate on beer preference and popularity across the US reveals nuanced findings. While we found small differences in beer ratings across climates, the overall trends remained remarkably consistent, suggesting a shared American identity that transcends geographical variations in climate. It appears that, irrespective of whether Americans live in colder or warmer climates, certain preferences in beer evaluation persist, hinting at a cultural bias that unites beer enthusiasts across the nation.

Furthermore, our investigation into ABV levels presented intriguing correlations with climate. In regions characterized by hotter summers, reviewers rather drink higher ABV beers whilst individuals in colder climates may indeed consume more beers, but these beverages tend to exhibit lower ABV levels. However, it is important to acknowledge potential confounding factors like economic factors and supplier-driven influences that may have influenced our observations. Indeed, financial factors could impact both the quantity and quality of beer consumption which would also depend on the types of beers available in different regions. In essence, while our current findings offer interesting insights, further investigations of these potential confounders would enhance the depth of our understanding of the intricate interplay between climate and beer preferences.
