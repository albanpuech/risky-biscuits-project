# Pints and Patterns: How Climate Shapes U.S. Beer Ratings

## Introduction

🍻 Welcome to "Pints and Patterns: How Climate Shapes U.S. Beer Ratings"!

Get ready for a tasty and refreshing adventure! In this project, we are going to pop the cap off the worlds of beers and climate! 
Who hasn't dreamed of a cold beer on a warm summer's evening? Does a chilly breeze call for a stronger brew? These questions made us wonder: Perhaps our beer tastes change with the climate we're in!
We will take you on a bubbly journey to explore how the sunny beaches, snowy mountains, and everything in between across the U.S. influence the way Americans rate their favorite beers!

The questions we will be answering include:
- Is there a correlation between climate and the overall beer reviews?
- Does climate influence people's demand for taste, palate and aroma?
- How does beer ratings change across seasons in the different climate areas?

## Dataset
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

## How does the average ratings of the 5 most rated beers in the US change across the climate regions?

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


## Climate and Average Beer Scores

One first step into exploring how climates and beer scores are related would be to look closer at the different sub-scores that, put together, give the beer ratings that we have been looking at up until now!

On Beer Advocate as on Beer Ratings, users are asked to score beers on the four following aspects:


  
| Score      | Description                           | Scale |
|------------|---------------------------------------|-------|
| Aroma      | The overall smell of the beer.        | 0 to 5|
| Appearance | How the beer looks.                   | 0 to 5|
| Taste      | The overall flavor of the beer.       | 0 to 5|
| Palate     | The feel of the beer in the mouth.    | 0 to 5|



What's super exciting at this point is that we can start looking a bit deeper into the differences in beer ratings across climate zones by looking at each of these aspects!

## How does the favorite styles of beer change across climate regions?

## How does the overall review sentiment change across climate regions?








[1] https://drive.google.com/drive/folders/1Wz6D2FM25ydFw_-41I9uTwG9uNsN4TCF \
[2] https://weatherandclimate.com/united-states
[3] Updated world map of the Köppen-Geiger climate classification, M. C. Peel, B. L. Finlayson, and T. A. McMahon

