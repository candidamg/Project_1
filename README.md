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
* Does the Gameplay time [length to complete the game] mean the game will receive a higher rating.
* The longer the video game the higher the score.
* What is the highest rating gameplay timeframe? 


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

## Impact of Metacritic Rating
We created a scatterplot measuring Metacritic Rating and Playtime, in hours to determine if there was a correlation.  There was a linear relationship.  All of the games that were played 30 or more hours had a Metacritic rating of at least 75, and all games that had 40 or more hours played had a Metacritic rating above 80.
