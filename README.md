### Project_1
Group_3_Module_7

Group due date: 2/12/2023

## Project Title: Videogames Data Review

## Team Members: 
* Max Atherton
* Candida Miranda
* Rachel Novak
* Christopher Winn

## Project Description/Outline:
* Videogames 
* Gameplay time
* Correlation between the lenght of the videogame and the score
* Game played the most number of times vs gametime played total


## Research Questions to Answer:
* Using playtime as a measure of the quality and popularity of a game, which metrics are most correlated with increased playtime?
* Which metrics are most correlated with Metacritic Rating.
* What is the distribution of playtime?


## Dataset used: 
RAWG API (https://rawg.io/apidocs)

## Rough Breakdown of Tasks: 
* python code bones
* API information-data_set research
* Visualizations
* Writen report
* Presentation outline

## Data Pull (Python)
We began by importing the following dependencies
* Pandas
* Requests 
* JSON
* Matplotlib 
* Numpy
* Time
* Scipy.stats
* Pprint

We then set up our URL information for our API call.  The base url for the Rawg API is 'https://api.rawg.io/api' To pull information, users also need an API Key.

One of the challenges we faced with this particular API was that game information was returned in pages.  The default result was 20 games per page, which, obviously, would not provide a meaningful number of games for analysis.  Our group utilized a for loop to create multiple urls to retrieve data from multiple pages.  We received data from 105 pages, which gave us 2,100 games to analyze.
The following attributes were then printed to a dataframe
* Game name
* Metacritic rating
* Release Date
* Recommendation (Rating)
* Recommendation Count
* Playtime
* Latest Update
* Users Added
* Game Owned (#)

To reduce the number of outliers, we created a new dataframe based on playtime hours being <= 60 hours.

We then created several plots to analyze the data and address our questions.

## Impact of Various Metrics on Playtime

We created a histogram to show the average playtime, in hours.  The mean playtime for our sample of games was 5.11 hours.  The distribution was skewed significantly to the right.

We created a scatterplot measuring Metacritic Rating and Playtime, in hours to determine if there was a correlation.  A linear regression model returned a slope of .33.  The vast majority of games had playtime less than 20 hours.  All of the games that were played 30 or more hours had a Metacritic rating of at least 75, and all games that had 40 or more hours played had a Metacritic rating above 80.

Our next scatterplot measured Recommendation Count and Playtime, in hours.  The linear regression model returned a slope of 24.85.

We then created a scatterplot to measure the Number of Users who owned the game vs Playtime.  The slope on the linear regression was 64.75.

The final scatterplot involving playtime measured Users Added and Playtime, in hours.  The slope for this linear regression was 128.53.

The regression lines on the scatterplot diagrams can be somewhat misleading, due to the scale.  Of all the metrics we measured against playtime, the slope of the metacritic rating was closest to 1, suggesting the strongest relationship.

We then examined metacritic rating against metrics to determine if there were any relationships there.  

The first scatterplot was Recommendation Count against Metacritic Rating.  The slope for this linear regression was 17.02.

Next, we examined the Number of Users who owned the game against Metacritic.  The slop of the linear regression for this analysis was 43.28.

The final scatterplot was Users Added against Metacritic Rating.  The slope for this linear regression was 86.7.

Of these three metrics, the strongest relationship appears to be between Recommendation Count and Metacritic Rating.
