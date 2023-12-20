

# Pints and Patterns: How Climate Shapes U.S. Beer Ratings


![image](https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/baneer.png?raw=true)


## 🍻 Introduction
Welcome to "Pints and Patterns: How Climate Shapes U.S. Beer Ratings"!

Get ready for a tasty and refreshing adventure! In this project, we are going to pop the cap off the worlds of beers and climate! 
Who hasn't dreamed of a cold beer on a warm summer's evening?  This question made us wonder: Maybe our beer tastes change with the climate we're in!
We will take you on an exciting journey to explore how the sunny beaches, snowy mountains, and everything in between across the U.S. influence the way Americans rate their favorite beers!

The questions we will be answering include:
- Is there a correlation between climate and the overall beer reviews?
- Does climate influence people's demand for taste, palate and aroma?
- How does beer ratings change across seasons in the different climate areas?

## 🍻 Dataset
### Reviews
The dataset we will be using contains x reviews from two major beer ratings platforms, namely, Beer Advocate and Beer Review.
These reviews were posted by more than x unique American inhabitants, on a time period spanning the years x to x. The dataset is available at [1].

### Climate
We use the Köppen climate classification data of the US states. The dataset was obtained from [2]. This climate classification is one of the most widely used ones.

It divides climates into five groups, which defines the first letter of the names of the climate classification groups. These are:
- A (tropical)
- B (arid)
- C (temperate)
- D (continental)
- E (polar)

All climates except for those in the E group are assigned a seasonal precipitation subgroup that defines the second letter, while the third one indicates the temperature subgroup [3]. All in all, we obtain the following categories:

| Köppen climate classification scheme | 1st | 2nd                 | 3rd              |
|--------------------------------------|-----|----------------------|------------------|
| **A (Tropical)**                     |     | f (Rainforest)       |                  |
|                                      |     | m (Monsoon)          |                  |
|                                      |     | w (Savanna, dry winter) |              |
|                                      |     | s (Savanna, dry summer) |              |
| **B (Dry)**                          |     | W (Arid Desert)      | h (Hot)          |
|                                      |     | S (Semi-Arid or steppe) | k (Cold)      |
| **C (Temperate)**                    |     | w (Dry winter)       | a (Hot summer)   |
|                                      |     | f (No dry season)    | b (Warm summer)  |
|                                      |     | s (Dry summer)       | c (Cold summer)  |
| **D (Continental)**                  |     | w (Dry winter)       | a (Hot summer)   |
|                                      |     | f (No dry season)    | b (Warm summer)  |
|                                      |     | s (Dry summer)       | c (Cold summer)  |
|                                      |     |                      | d (Very cold winter) |
| **E (Polar)**                        |     | T (Tundra)           |                  |
|                                      |     | F (Ice cap)          |                  |

## 🍻 How does the average ratings of the 5 most rated beers in the US change across the climate regions?

Beer tastes surely are very subjective. Even among groups of close friends, starting a debate about beer tastes at dinner can be as risky as bringing up politics and religion at Thanksgiving! We have all heard of entire families getting destroyed and torn apart after children revealed their "beer orientation" to their parents.

Motivated by those stories, and aware of the power that was into our hands with our best data analysis tools, we realized the impact that we could have on resolving one of today's major challenge: avoiding Stanford graduates getting disavowed by their parents after they come back with their beer tastes totally changed by the warm climate of the Bay Area, that often pushes them to switch to lighter beers to go well with their weekly barbecues.

We first looked at the top 5 most rated beers in the US:

  
| beer_name                     | mean rating | count | location of the brewery  |
|-------------------------------|-------------|-------|--------------------------|
| Brooklyn Black Chocolate Stout| 4.055809    | 2522  | United States, New York  |
| Trappistes Rochefort 10       | 4.391764    | 2483  | Belgium                  |
| AleSmith Speedway Stout       | 4.327619    | 1575  | United States, California|
| Delirium Tremens              | 4.069993    | 1443  | Belgium                  |
| Blind Pig IPA                 | 4.364850    | 1367  | United States, California|


Fun Fact: With two beers in the 5 most reviewed beers in the US, Belgian beers seem to be quite popular in the US!

These beers are the most reviewed ones, but they don't seem to have really high scores! In fact, we can see that beers with a large average review seem to be the ones with fewer reviews:

<p align="center">
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Distribution%20of%20the%20number%20of%20reviews%20for%20the%20beers%20having%20an%20average%20rating%20of%20more%20than%204.png?raw=true" width="600" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

What we are interested in however is to check if these ratings significantly change across climate zones. At first sight, it is quite complicated to draw any conclusion based on a visualization of the data alone:

<p align="center">
  <br>
  <img src="https://raw.githubusercontent.com/albanpuech/risky-biscuits-project/master/assets/img/Mean%20overall%20rating%20for%20each%20beer%20of%20the%20top%205%20and%20each%20climate%20zone.png" width="1000" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

We can run a chi-squared test to check if the difference in mean rating of each of the 5 most rated beer across the climate zones is statistically significant. These are the results that we obtain:

  
| Beer                            | P-value    | Statistically Significant? |
|---------------------------------|------------|----------------------------|
| Blind Pig IPA                   | 0.0194     | Yes                        |
| AleSmith Speedway Stout         | 0.0130     | Yes                        |
| Brooklyn Black Chocolate Stout  | 0.9298     | No                         |
| Trappistes Rochefort 10         | 0.0344     | Yes                        |
| Delirium Tremens                | 0.9948     | No                         |


What do we see in this table? Well... 3 beers have a mean rating that significantly changes across climate zones! Does that tell us anything about whether the climate impacts beer ratings? No! In the remaining of this project, we want to explore some more the hidden links between climate and beer ratings...


## 🍻 Climate and Average Beer Scores

One first step into exploring how climates and beer scores are related would be to look closer at the different sub-scores that, put together, give the beer ratings that we have been looking at up until now!

On Beer Advocate as on Beer Ratings, users are asked to score beers on the four following aspects:


| Score      | Description                           | Scale |
|------------|---------------------------------------|-------|
| Aroma      | The overall smell of the beer.        | 0 to 5|
| Appearance | How the beer looks.                   | 0 to 5|
| Taste      | The overall flavor of the beer.       | 0 to 5|
| Palate     | The feel of the beer in the mouth.    | 0 to 5|


What's super exciting at this point is that we can start looking a bit deeper into the differences in beer ratings across climate zones by looking at each of these aspects! 


For each climate region, we can perform a t-test to see if there is a statistically significant difference in mean between its mean scores , and the mean scores of the reviews from the whole country. We show the p-values in the following table:

[INSERT P VALUE TABLE HERE from the ]

We can then display the mean score for each category and each climate zone, keeping only the ones that show a statistically significant difference with the mean score computed over the whole country:

#TODO Change this plot to show par plots instead (doesnt make sense to link the points to me)
![image](https://github.com/albanpuech/risky-biscuits-project/assets/72336171/60ccdc71-e31d-4400-a611-4993cb9242d7)

For every score, we observe differences in the average rating between a few climate zone and the country-level average. However, we cannot see a clear pattern between climated and ratings. We thus decide to group climate zones into larger groups based on the climate scheme, the seasonal precipitation, and the summer heat level. We assign the different climates to the different categories as followed:


| climate | scheme      | seasonal_precipitation | heat_level  |
|---------|-------------|------------------------|-------------|
| Cfa     | Temperate   | without dry season     | hot summer  |
| Dfb     | Continental | without dry season     | warm summer |
| Dfa     | Continental | without dry season     | hot summer  |
| Csa     | Temperate   | with dry season        | hot summer  |
| Dsb     | Continental | with dry season        | warm summer |
| Dfc     | Continental | without dry season     | cold summer |
| Csb     | Temperate   | with dry season        | warm summer |
| Bsk     | Dry         | with dry season        | cold summer |
| Cfb     | Temperate   | without dry season     | warm summer |
| Dsc     | Continental | with dry season        | cold summer |


### Focusing on climate schemes instead of climate zones

We first work with the scheme categories.
We perform a chi-squared test to check if the different climate scheme show significantly different mean scores for the 4 categories. 

#TODO I think there is an issue with these results, no?

| Score Category | P-value                    | Statistically Significant? |
|----------------|----------------------------|----------------------------|
| Aroma          | 1.0991290603490593e-38     | Yes                        |
| Appearance     | 1.7394357136527266e-52     | Yes                        |
| Palate         | 7.648038295249008e-29      | Yes                        |
| Taste          | 1.7962281611299406e-44     | Yes                        |
| Overall        | 2.358910645578224e-35      | Yes                        |


The results show that in all the cases, except appearance,  the average rating decreases from temperate to continental and to dry. In contrast, appearance increases from 3.92 to around 3.95. The tests are all statistically significant.
Within each climate category — be it temperate, continental, or dry — climates may either experience a dry season or not, adding a layer of variation within the same scheme.

[Peaople don't leave the same way blablabla]

This is the second level of the Kopper climate classification

[INSERT RESULTS OF SEASONAL PRECIPITATION HERE]

[We can also look at the heat level]
[DEF heat level]

HEAT LEVEL chi2 test : overall rating for hot summer, warm summer, cold summer (c)
Result: there is a statistically significant difference between the overall, taste, appearance… parameters within each HEAT LEVEL. 

It also looks like appearance is less affected by the HEAT LEVEL compared to for example the aroma, which is the most varying parameter. 

Just by plotting the overall score it seems like the hotter it is the more people like beer
Even when plotting all the other parameters (tate, appearance,...) it seems like people prefer beer when in a hot environment

Observation: in all the conditions the variation between the ratings are very little (between 0.02-0.06). The difference is that with this approach we analyzed groups of beers much bigger (combination of different climates) compared to what we did before when we looked at the average rating for each different climate. This can explain the fact that before, the average ratings across the climates varied more (about 0.3) compared to this approach.

## 🍻 Climate and styles of beers 

Having unraveled the preliminary layers of our investigation into the impact of climate trends on beer reviews, we now pivot our analytical lens towards the intricate world of beer types. The initial exploration revealed a fascinating tapestry of how overall ratings, taste, aroma, appearance, and smell are influenced by varying climatic conditions. However, understanding the nuanced relationship between climate and beer preference necessitates a deeper dive into the categorical realm of beers. Do users from certain climates thrive on certain styles of beers, reflecting a harmonious marriage of flavour profiles and atmospheric conditions?

### Making the beer type mapping

In order to make this mapping, we need to map each specific type of beer to a general style. This uses a mapping done manually which relates each beer to a general style of beer according to an article by EHL (https://hospitalityinsights.ehl.edu/beer-types). The ten styles are: Lager, Pale Ale, Blonde Ale, Brown Ale, IPA, Wheat beer, Porter, Stout, Sour Ale, Scottish Ale.

We are interested in the popularity of the beers as well as the preferred beer. Therefore we approximate the popularity of a given beer by the number of reviews it received, although it is important to note that these are slightly different. Indeed, we cannot infer the exact number of beers drank, but, since we have a big enough sample, we can approximate it by the number of reviews received.

For the computation of the best beers, we first created a new dataframe for each climate from which we grouped by general style. Then, we calculated the mean of the overall score for each beer and we sorted in an ascending sequence. From this point we kept only the 3 beers with the highest overall score for each climate, considering them the best beers in the different conditions.

### Climate and beer style 

First, lets take a look at the overall ratings given to each beer by the respective climates. On this plot, we've added three different averages. These are: 

- beer macro average: mean of the overall averages per climate for each beer type
- macro average: mean of the overall averages per climate for all beers
- micro average: mean of all the overall averages 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/assets/95092676/88210c08-2bd3-4f0f-821d-10912938825a raw=true" width="1000" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

This plot can make us think that there are significant variabilities between the approval of the various beer styles by the different climates. Therefore, we perform a ranking of the beer styles and most popular beer styles to investigate this. When ranking the best beers per climate group, however, we can immediately notice that there is very little variability between the climate groups! For instance, Sour Ale is the common best rated beer followed by Stout. For all climates apart from Csb and Dfc where it is Porter, the third best rated beer is IPA. On the other hand, the most popular beers are very different from the best rated beers with IPA in first place and Pale Ale in second. Variability is also low and only affects ranks 3-8. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/assets/95092676/05e4d3c0-4a26-4752-9fb0-629a64cfbe57 raw=true" width="700" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

Indeed, when looking at the average position of each beer style, Sour Ale is first with 1.0, followed by Stout with 2.0, IPA with 3.2 and Porter with 3.8. However, when observing the most rated beers, Sour Ale is not even in the top three! Its average position is in fact 5.4. The top four are IPA with 1.0, Pale Ale with 2.0, Brown Ale at 3,3 and Porter at 3.7. This means that the most popular beer is not necessarily the most preferred. 

Although these are only small varibilites, we chose to investigate these with the different climate factors to see if they might be more consequential. However, for the three categories that are climate schemes, seasonal precipitations and heat levels, the top three beers are the same (Sour Ale, Stout, IPA) and so are the most rated beers (IPA, Pale Ale, Brown Ale).

In summary, the ratings given to the beer styles between the various climates are significantly different. But, the ratings of the beer styles for the different climate factors are very similar. Therefore, the beer styles' ranking doesn't seem to be affected by the climate. This can make us think that there is a different appreciation of the beers in general (ie. higher or lower ratings for all beer styles), but the order of their preferance is the same. We therefore need to find a new parameter to investigate that could clarify the difference in ratings given to the various beers.  

## 🍻 Climate and Alcohol Level of Beers

A group of researchers at the University of Pittsberg (https://dom.pitt.edu/people-drink-more-in-colder-regions-bataller-led-study-finds/) found a negative correlation between climate factors and alcohol consumption. This means that, as climate factors like temperature drop, the average alcohol consumption increases. But does this mean that the average drink’s alcohol level rises or rather that people drink more alcoholic drinks in general? Let’s investigate!

### Focusing on ABV per climate

In order to do so, let’s study the ABV (alcohol by volume) rating for each beer and find possible correlations between it and the climate factors. We use the number of rankings given to a beer as a measure of popularity and their overall score as a measure of preference. As for the climate factors, we use the ones described earlier: climate, scheme, seasonal precipitation, heat level.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/abv_all_bears.png?raw=true" width="200" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

As shown on the boxplot, the rated beers are centred around a mean ABV of 7.00 and half are contained in the [5.4 ; 8.0] range. We want to know how this distribution differs in the different climate categories. When testing the difference in mean ABV for each climate, the results are not significant. Therefore, we group the beers by general beer type and climate. This uses the same mapping as before.

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/assets/95092676/5c94d2f5-e246-46d0-862b-04721335acdb raw=true" width="800" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

TEXT ANALYSING BOXPLOTS

First, we compare the popularity and preference of the beers in the different climate conditions based on their ABV. From the grouped beers, we find the three most liked beer styles and the three most reviewed. 

<p align="center">
  <br>
  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Mean%20abv%20of%20the%203%20most%20reviewed%20beers%20for%20each%20climate.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">  <img src="https://github.com/albanpuech/risky-biscuits-project/blob/master/assets/img/Mean%20abv%20of%20the%20best%203%20beers%20for%20each%20climate.png?raw=true" height="300" title="Distribution of the number of reviews for the beers having an average rating of more than 4">
</p>

The ABV mean is significantly different across the climates (between 0.4% and 1%) which means that users in different climates drink beers with diverse levels of alcohol. We can also note that the three most liked beers are always out of five from the original ten styles. For the most reviewed, these are only four styles out of the total 10 and are different than the 5 most liked. We indeed find that there is a statistical difference between the best beer and the most reviewed beer in each climate. This means that the most drunken beers are different than the types of beer preferred. 

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

