

# Cheers to Latitude: A Journey Through Climate and Beer preferences


![image](https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/baneer.png?raw=true)


## 🍻 Introduction


### Beer Reviews

If you live in Switzerland and have ever been to South America, you have probably noticed that people are more outgoing, warmer and approachable there. Well, that’s not just your perception : the climate you live in really does shape your personality. In fact, research shows that if you live in a warmer climate, you tend to have greater social tendencies, emotional stability, extroversion, and openness to new experiences ([Wei et al., 2017](https://www.nature.com/articles/s41562-017-0240-0)). 

If climate makes us different there is for sure something that we all share : our love for beers. Yes, the amber elixir that brings people together across continents. But, hang on, could there be a mysterious link between the climate that molds our personalities and the way we savor our beers? 

In order to answer this enigmatic question we need data ! Thankfully for us, people around the world have been rating beers for a long time on websites like Beer Advocate or Rate Beer. 

<p align="center">
  <img src="https://cdn.beeradvocate.com/im/meta/beeradvocate-meta-respect-beer-logo.png" width="100" title="Example review coming from Beer advocate"> 
    <img src="https://www.ratebeer.com/images/logos/login-logo.png" width="100" title="Example review coming from Beer advocate">
</p>

From these plateforms, we gathered 1.6M reviews from 22.8K american users evaluating 134 different beers [1]. 
A complete review looks like this:

<p align="center">
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/ex_review.png?raw=true" width="600" title="Example review coming from Beer advocate">
</p>

A review contains the following information:
- The **name** of the beer.
- The **style** of the beer.
- The **alcohol** by volume.
- The **name** of the breweries and its location.
- the **username** of the author and its location.
- a **rating** incidated in red, that ranges from 1 to 5.
- The difference, denoted **rDev**, between the rating given by the user and the average rating of the beer considering all reviews it received.
- A list of 5 scores: **look**, **smell**, **taste**, **feel**, and **overall**. Note that the Rating is not directly obtained from these, nor is the "overall" related to the other subscores. These also range from 1 to 5.
- The **text** of the review.
- The **date** and **hour** when the review was posted.

### Climate Data

As we are interested in studying the impact of climate on the beer reviews, we have to choose what climate data to use. While many climate classification exist, we'll be using the popular Köppen climate classification. 

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
 
From this plot, even though all ratings have a  difference, we can see that each subrating follows the same trends. In other words, each climate seems to rate the beers in a certain range for all of the subratings. This means that each climate has a certain coherence in the ratings it gives which shows its general appreciation of beers compared to one certain aspect of it. 

For instance, the Csa and Dfa climates always has a mean rating above both the micro and macro averages. These climates have a hot summer which might make the users more incline to appreciate beers in general because of the social aspect and simple appreciation of a cold drink on a hot summer day. On the other hand, Dsb and Dsc climates give ratings under the averages. Both of these are continental and Dsc, with only Idaho, has a cold summer. Would it then be the case that people living in colder climates have higher beer expectations and standards?

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


Climate scheme: 
Hot and warm summers show very similar average scores. There however is a much larger difference with cold summer which shows lower scores across all categories.

### Conclusion on climate and reviews

- There appears to be a correlation between the climatic conditions and the average ratings.

- Climate is known to influence personality traits, and it may also influence beer preferences.

- What we have seen is that areas with hot summers also have larger beer scores, which could may be because of the social and refreshing aspects of beer consumption in warmer areas

- We have also observed that colder climates are associated to lower scores, which may come from the fact that that people in colder climates have higher expectations or different standards of beers. This may be because they put more emphasis on the quality or taste of beers. 

- The appearance score was the most stable one across the difference climate regions, maybe because it is also the criteria that is the hardest to rate, as opposed to the palate and the taste that may have more importance than the other criterion.

## 🍻 Climate and styles of beers 

Having unraveled the preliminary layers of our investigation into the impact of climate trends on beer reviews, we now pivot our analytical lens towards the intricate world of beer types. The initial exploration revealed how overall, taste, aroma, appearance, and palate ratings are influenced by varying climatic conditions. However, understanding the nuanced relationship between climate and beer preference necessitates a deeper dive into the categories of beers. Do users from certain climates thrive on certain styles of beers?

### Making the beer type mapping

In order to make this mapping, we need to map each specific type of beer to a general style. This uses a mapping done manually which relates each beer to a general style of beer according to an article by EHL (https://hospitalityinsights.ehl.edu/beer-types). The ten styles are: Lager, Pale Ale, Blonde Ale, Brown Ale, IPA, Wheat beer, Porter, Stout, Sour Ale, Scottish Ale. Here is the overall ranking of each beer type for the whole US.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/styles_beer.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

We are interested in the popularity of the beers as well as the preferred beer. Therefore we approximate the popularity of a given beer by the number of reviews it received, although it is important to note that these are slightly different. Indeed, we cannot infer the exact number of beers drank, but, since we have a big enough sample, we can approximate it by the number of reviews received.

For the computation of the best beers, we first created a new dataframe for each climate from which we grouped by general style. Then, we calculated the mean of the overall score for each beer and we sorted in an ascending sequence. From this point we kept only the 3 beers with the highest overall score for each climate, considering them the best beers in the different conditions.

### Climate and beer style 

First, let's take a look at the overall ratings given to each beer by the respective climates. On this plot, we've added the micro average.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/beer_type_average_ratings.png?raw=true" max-height="600" title="Overall beer rankings per beer style as a function of the climate">   
</p>

This plot can make us think that there are significant variabilities between the approval of the various beer styles by the different climates. Therefore, we perform a ranking of the beer styles and most popular beer styles to investigate this. When ranking the best beers per climate group, however, we can immediately notice that there is very little variability between the climate groups! For instance, Sour Ale is the common best rated beer followed by Stout. For all climates apart from Csb and Dfc where it is Porter, the third best rated beer is IPA. On the other hand, the most popular beers are very different from the best rated beers with IPA in first place and Pale Ale in second. Variability is also low and only affects ranks 3-8. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/style_ranking_best_beer.png?raw=true" max-height="200" title="Average position of each beer, ranked by overall rating">   
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/style_ranking_popularity.png?raw=true" max-height="200" title="Average position of each beer, ranked by number of reviews">
</p>

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

As shown on the boxplot, the rated beers are centered around a mean ABV of 7.00°, and half are contained in the [5.4°, 8.0°] range. We want to know how this distribution differs in the different climate categories. 

First, we compare the popularity and preference of the beers in the different climate conditions based on their ABV. From the grouped climates, we find the three most liked beer styles and the three most reviewed. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Mean%20abv%20of%20the%203%20most%20reviewed%20beers%20for%20each%20climate.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Mean%20abv%20of%20the%20best%203%20beers%20for%20each%20climate.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>
s
By looking at the two U.S. maps here above, we can see that there is variation in the abv average between the best beers and the most reviewd beers. It results that for the preferred beers the abv mean is higher than for the most populars. cIn both cases, we can ob
abv_map_climate.pngin the abv , d to be easily interpreted. We therefore look at the three disctict categories. The ABV mean is significantly different across the climates (between 0.4% and 1%) which means that users in different climates drink beers with diverse levels of alcohol. 


We can also note that the three most liked beers are always out of five from the original ten styles. For the most reviewed, these are only four styles out of the total 10 and are different than the 5 most liked. We indeed find that there is a statistical difference between the best beer and the most reviewed beer in each climate. This means that the most drunken beers are different than the types of beer preferred. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Average%20abv%20of%20the%203%20most%20reviewed%20beers%20for%20each%20climate%20scheme.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">   <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Average%20abv%20of%20the%203%20best%20beers%20for%20each%20climate%20scheme.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

When observing the climate schemes, we can notice that both the best rated beers and the most reviewed beers have a higher ABV in a temperate climate than a dry one. The type of curves and slopes are similar to the previous analysis for the average rating as a function of the ABV. This could be further investigated to find a possible correlation between the ABV and rating given as a function of the climate scheme. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Average%20abv%20of%20the%203%20most%20reviewed%20beers%20for%20each%20climate%20heating.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Average%20abv%20of%20the%20best%203%20beers%20for%20each%20climate%20heating.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

For the seasonal precipitation groups, the best beers have a higher ABV in locations without a dry season than in those with. Again, in this case, curves and slopes are similar to previous cases for the average rating of ABV. In contrast, we can notice that, for the most reviewed beers, there is an increase in ABV for regions with dry seasons. We could further analyse the overall rating in terms of the ABV and seasonal precipitation. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Average%20abv%20of%20the%203%20most%20reviewed%20beers%20for%20each%20climate%20precipitation.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Average%20abv%20of%20the%20best%203%20beers%20for%20each%20climate%20precipitation.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

Lastly, when observing the heat levels of the different climates, we obtain the same type of curves and slopes as in the previous case for the average rating for the best beers. The average of the abv of the three best beers is higher for locations with hot summers, slightly less for warm summers and substantially less for cold summers. For the most reviewed beer, again hot summer has a higher abv but for warm and cold we have the same abv. A further investigation can be performed to find a correlation between the ABV and rating given.

### Correlation between ABV and rating 

As we notice that most climate factors have a similar trend with the rating in terms of the ABV of the beer types, we are curious to know if these ratings depend on the climate factor or rather simply on the ABV. We are therefore looking for a correlation between the ABV and rating. 

weird results, to be done further




[1] https://drive.google.com/drive/folders/1Wz6D2FM25ydFw_-41I9uTwG9uNsN4TCF \
[2] https://weatherandclimate.com/united-states
[3] Updated world map of the Köppen-Geiger climate classification, M. C. Peel, B. L. Finlayson, and T. A. McMahon

