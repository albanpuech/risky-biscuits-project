

# Cheers to Latitude: A Journey Through Climate and Beer preferences


![image](https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/baneer.png?raw=true)


## 🍻 Introduction


### Beer Reviews

If you live in Switzerland and have ever been to South America, you have probably noticed that people are more outgoing, warmer and approachable there. Well, that’s not just your perception: the climate you live in really does shape your personality. In fact, research shows that if you live in a warmer climate, you tend to have greater social tendencies, emotional stability, extroversion, and openness to new experiences ([Wei et al., 2017](https://www.nature.com/articles/s41562-017-0240-0)). 

If climate makes us different there is for sure something that we all share: our love for beer. Yes, the amber elixir that brings people together across continents. But, hang on, could there be a mysterious link between the climate that molds our personalities and the way we savor our beers? 

In order to answer this enigmatic question we need data! Luckily, people around the world have been rating beers for a long time on websites like Beer Advocate or Rate Beer. 

<p align="center">
  <img src="https://cdn.beeradvocate.com/im/meta/beeradvocate-meta-respect-beer-logo.png" width="100" title="Example review coming from Beer advocate"> 
    <img src="https://www.ratebeer.com/images/logos/login-logo.png" width="100" title="Example review coming from Beer advocate">
</p>

From these platforms, we gathered 1.6M reviews from 22.8K American users evaluating 134 different beers ([dataset](https://drive.google.com/drive/folders/1Wz6D2FM25ydFw_-41I9uTwG9uNsN4TCF)). 
A complete review looks like this:

<p align="center">
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/ex_review.png?raw=true" width="600" title="Example review coming from Beer advocate">
</p>

A review contains the following information:
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

### Climate Data

As we are interested in studying the impact of climate on the beer reviews, we have to choose what climate data to use. While many climate classifications exist, we'll be using the popular Köppen climate classification. 

<p align="center">
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/us%20climate.png?raw=true" width="600" title="Climate US">
</p>

Let's look at the climates in the US. There are 10 different climates in the US. These are:

| Climate | Seasonal precipitation                 | Temperature             |
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
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/overall_climate.png?raw=true" height="300" title="Subratings of all beers per climate">
</p>

We can also look at the other scores:
<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/climate_average_ratings.png?raw=true" height="300" title="Subratings of all beers per climate">
</p>

Keeping in mind that the y-axis does not start at zero on these plots, we still observe a difference of around 4 percent in the mean overall score across climates.

From this plot, even though all ratings have a difference, we can see that each sub-rating follows the same trends. This means that if there were an influence of climate on the scores, climate would impact

For instance, the Csa and Dfa climates always has a mean rating above both the micro average. These climates have a hot summer which might make the users more incline to appreciate beers in general because of the social aspect and simple appreciation of a cold drink on a hot summer day. On the other hand, Dsb and Dsc climates give ratings under the averages. Both of these are continental and Dsc, with only Idaho, has a cold summer. Would it then be the case that people living in colder climates have higher beer expectations and standards?

Looking at the plot of the climates zones in the US, we can see that Dsb and Dsc only cover two states: Idaho and Washington. We can also check the number of reviews per climate

<p align="center">
  <br>
  <img src="assets\img\Number of ratings per climate.png" height="400" title="Average score for climate schemes">
</p>

We thus have to group the climates zones together if we want to have enough beers in each of the groups. This is what we are going to explore next!

### Climate factors and beers

In this part, we regroup the climate zones based on their scheme, seasonal precipitation, and summer heat level. 

Dry climates show smaller average overall, aroma, taste and palate scores than the other climates. However, the appearance scores are much more similar across temperate, continental and dry climates.


<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_scheme.png?raw=true" height="600" title="Average score for climate schemes">
</p>

We can also look at the precipitation levels:


<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_preci.png?raw=true" height="600" title="Average score for climate precipitations">
</p>

And at the summer temperature:

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/avg_score_temp.png?raw=true" height="600" title="Average score for climate temepratures">
</p>


Climate scheme: Hot and warm summers show very similar average scores. There however is a much larger difference with cold summer which shows lower scores across all categories.

### Conclusion on climate and reviews

- There appears to be a correlation between the climatic conditions and the average ratings.

- Climate is known to influence personality traits, and it may also influence beer preferences.

- What we have seen is that areas with hot summers also have larger beer scores, which could may be because of the social and refreshing aspects of beer consumption in warmer areas

- We have also observed that colder climates are associated to lower scores, which may come from the fact that that people in colder climates have higher expectations or different standards of beers. This may be because they put more emphasis on the quality or taste of beers. 

- The appearance score was the most stable one across the difference climate regions, maybe because it is also the criteria that is the hardest to rate, as opposed to the palate and the taste that may have more importance than the other criterion.

## 🍻 Climate and styles of beers 

Having unraveled the preliminary layers of our investigation into the impact of climate trends on beer reviews, we now pivot our analytical lens towards the intricate world of beer types. The initial exploration revealed how overall, taste, aroma, appearance, and palate ratings are influenced by varying climatic conditions. However, understanding the nuanced relationship between climate and beer preference necessitates a deeper dive into the categories of beers. Do users from certain climates thrive on certain styles of beers?

There exists a lot of beer styles, just in our dataset there was 130 of them. To have more meaningful analysis we mapped them to 10 general styles. The ten styles are: Lager, Pale Ale, Blonde Ale, Brown Ale, IPA, Wheat beer, Porter, Stout, Sour Ale, Scottish Ale. Here is a visualization of the style's ranking :

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/styles_beer.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

**Fun fact**: This mapping was done performed manually following an article by EHL (https://hospitalityinsights.ehl.edu/beer-types). 👍

First, let's take a look at the overall ratings given to each beer by the respective climates. On this plot, we've added the micro average, i.e. the overall mean over the climates.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/beer_type_average_ratings.png?raw=true" max-height="600" title="Overall beer rankings per beer style as a function of the climate">   
</p>

There are indeed significant variabilities between the overall score of the various beer styles by the different climates, leading us to think that people from certain climates prefer certain beer styles. However, when ranking the best beers per climate group, we could immediately notice that there is very little variability between the climate groups. 

Maybe the variability lies in the climate subgroups. To look into this, we computed the best ranked and the most popular beers per climate subgroup. Here are the results :
|             |  Scheme   |   Scheme     | Scheme   |
|-------------|-----------|--------------|----------|
|  Rank       | Temperate | Continental  |   Dry    |
|-------------|-----------|--------------|----------|
| **1st**     | Sour Ale  |  Sour Ale    | Sour Ale | 
| **2nd**     |   Stout   |    Stout     |  Stout   |
| **3rd**     |    IPA    |     IPA      |   IPA    |
| **4rd**     |   Porter  |    Porter    |  Porter  |
| **5rd**     | Brown Ale |  Brown Ale   |Brown Ale |
 
 

<table style="border-collapse: collapse; border: 2px double black;">
  <tr>
    <td></td>
    <td colspan="3">Scheme</td>
    <td colspan="2">Precipitation</td>
    <td colspan="3">Temperature</td>
  </tr>
  <tr>
    <td><b>Rank</b></td>
    <td>Temperate</td>
    <td>Continental</td>
    <td>Dry</td>
    <td>Without dry season</td>
    <td>With dry season</td>
    <td>Hot summer</td>
    <td>Warm summer</td>
    <td>Cold summer</td>

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

  </tr>
</table>



<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/style_ranking_best_beer.png?raw=true" max-height="200" title="Average position of each beer, ranked by overall rating">   
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/style_ranking_popularity.png?raw=true" max-height="200" title="Average position of each beer, ranked by number of reviews">
</p>

For instance, Sour Ale is the best rated beer followed by Stout. For all climates apart from Csb and Dfc where it is Porter, the third best rated beer is IPA. On the other hand, the most popular beers are very different from the best rated beers with IPA in first place and Pale Ale in second. Variability is also low and only affects ranks 3-8. 

Indeed, when looking at the average position of each beer style, Sour Ale is first with 1.0, followed by Stout with 2.0, IPA with 3.2 and Porter with 3.8. However, when observing the most rated beers, Sour Ale is not even in the top three! Its average position is in fact 5.4. The top four are IPA with 1.0, Pale Ale with 2.0, Brown Ale at 3,3 and Porter at 3.7. This means that the most popular beer is not necessarily the most preferred. 

Although these are only small varibilites, we chose to investigate these with the different climate factors to see if they might be more consequential. However, for the three categories that are climate schemes, seasonal precipitations and heat levels, the top three beers are the same (Sour Ale, Stout, IPA) and so are the most-rated beers (IPA, Pale Ale, Brown Ale).

ADD WORD CLOUD THAT CHARACTERISE THESE BEERS?

In summary, the ratings given to the beer styles between the various climates are significantly different. But, the ratings of the beer styles for the different climate factors are very similar. Therefore, the beer style rankings don't seem to be affected by the climate. This can make us think that there is a different appreciation of the beers in general (ie. higher or lower ratings for all beer styles), but the order of their preference is the same. We therefore need to find a new parameter to investigate that could clarify the difference in ratings given to the various beers.

One of the potential explanation for this is linked with the fact that the chosen general types regroup many different kind of beers in one. We decided to investigate the different statistics linked with the beers and to see if some had a big variation inside of each type. The one that came on top was the alcohol by volume (ABV) as one can see in the following plot.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_styles.png?raw=true" width="800" title="Horizontal boxplot of the ABV per beer style">
</p>

It appears that the ABV varies a lot even inside of each beer style. This could explain why the orders of the beer styles are the same between the climates but the ratings are different. Indeed, the ABV could be a parameter that is more important than the beer style itself. We therefore decided to investigate the ABV and its relation to the ratings given to the beers.

## 🍻 Climate and Alcohol Level of Beers

A group of researchers at the University of Pittsburgh (https://dom.pitt.edu/people-drink-more-in-colder-regions-bataller-led-study-finds/) found a negative correlation between climate factors and alcohol consumption. This means that, as climate factors like temperature drop, the average alcohol consumption increases. But does this mean that the average drink’s alcohol level rises or rather that people drink more alcoholic drinks in general? Let’s investigate!

### Focusing on ABV per climate

In order to do so, let’s study the ABV rating for each beer and find possible correlations between it and the climate factors. We use the number of rankings given to a beer as a measure of popularity and their overall score as a measure of preference. As for the climate factors, we use the ones described earlier: climate, scheme, seasonal precipitation, heat level.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_boxplot.png?raw=true" width="200" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

As shown on the boxplot, the rated beers are centered around a mean ABV of 7.0°, and half are contained in the [5.4°, 8.0°] range. We want to know how this distribution differs in the different climate categories. 

First, we compare the popularity and preference of the beers in the different climate conditions based on their ABV. From the grouped climates, we find the three most liked beer styles and the three most reviewed. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_climate.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4"> 
</p>

By looking at the two U.S. maps here above, we can see that there is variation in the ABV average between the best beers and the most reviewed beers. It results that for the preferred beers the ABV mean is higher than for the most populars. In both cases, we can observe a variability across the climates but again, too many climates at a time make the results hard to interpret. We will therefore analyse the three climate levels separately.

It is to be noted that for the three next plots, the range of the colorbar are not equals on the left and right plots. This was chosen to better visualize the differences inside of each plots and because the average ABV of the best beers are always higher than for the most reviewed ones.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_scheme.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4"> 
</p>

The resulting plots show a smaller ABV for the users living in a dry climate than for the ones living in a temperate or in a continental climate. This is true for both the best beers and the most reviewed beers. 

This seems counterintuitive as one could think people living in a colder climate drink beers that are lighter and not too alcoholic to create a warming sensation, whereas in a dry climate they drink beers with a higher ABV to provide a sensation of coziness. But an important point to be noted is that in our dataset, the only climate considered to be dry is a cold semi-arid climate, it does not opposite itself with the next analysis.


<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_precipitation.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4"> 
</p>

For the seasonal precipitation groups, the best beers have a higher ABV in locations without a dry season than in those with. In contrast, we can notice that, for the most reviewed beers, there is an increase in ABV for regions with dry seasons, but the difference is not as big as for the best beers.

One could assume that beers with less alcohol are more appreciated in dry season because they are more refreshing. However, this is not true for the most reviewed beers. 

These results could be mitigated by some confounders, mostly one can notice that the separation is East-West and there are way more reviews on the East coast than on the West coast. This could be due to the fact that the East coast is more populated than the West coast. Therefore, we cannot conclude that the climate is the only factor that influences the ABV of the beers.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_map_temperature.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4"> 
</p>

Lastly, when observing the temperature of summer, the ABV consummed is higher in regions with a hot summer than in those with a cold summer. This is true for both the best beers and the most reviewed beers. The variation is also the biggest among the different climate categories.



### Analysis of ABV

In all cases, we can notice that there is a small difference in ABV means. The typical differences is around 0.1° and the highest variation for one chosen climate category is when we compare hot and cold summer. 

The first main result we find is that U.S. citizens prefer beers with higher ABV compared to the most drank beers. This is true for all climate categories. Indeed, in the cases of the best beers, their average ABV was always above the global mean of 7°.

Then, we find that the ABV is higher in regions with a hot summer than in those with a cold summer. This is true for both the best beers and the most reviewed beers. This could seem opposite to the conclusions of the study by the University of Pittsburgh. However, we have to keep in mind that we are not studying the alcohol consumption but rather the alcohol level of the beers. Therefore, this could mean that people living in colder climates drink more beers but with a lower ABV.

# Conclusion

Part about always small differences but because americans are americans wether they live in a cold or hot climate.

Part about possible confounders to investigate: money, fournisseur (what kind of beers are sold where)

[1] https://drive.google.com/drive/folders/1Wz6D2FM25ydFw_-41I9uTwG9uNsN4TCF \
[2] https://weatherandclimate.com/united-states
[3] Updated world map of the Köppen-Geiger climate classification, M. C. Peel, B. L. Finlayson, and T. A. McMahon

