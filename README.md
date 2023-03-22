# nosql-challenge

This challenge focused on using Mongo to setup, update, and conduct an exploratory analysis on data from the UK Food Standards Agency.

### Part 1: Database Setup and Update

For this part I started by importing the JSON files from my terminal, then named the database and collection. After importing my dependencies, I created an instance of Mongo Client and pprinted a document from the collection to reference later in the challenge.

I then updated the database, adding a new restaurant to the collection which included searching the existing database to complete the document with the correct business type ID. I also removed the establishments located in Dover and updated all longitude and latitude values in the database to the correct data type.

### Part 2: Exploratory Analysis

For part two I needed to construct and run several queries to answer four questions regarding the information contained in this collection. 

The first two questions, which establishments have a hygiene score of 20 and which London establishments have a rating value greater than or equal to 4, required similar queries. The first required a simple find query, for which I excluded the “Meta” fields because most documents were missing this information, and then converted the results to a DataFrame. The second followed the same format but required two parts to the query.

Questions three and four required more complex queries. To find the top five establishments with a rating of five nearest a given location sorted by hygiene score I used a find query that contained separate query and fields arguments as well as a limit and sort parameters. The query found those documents with a rating equal to five and two arguments finding the geolocation. A separate search for latitude and longitude each included the upper and lower bounds of the search radius. Then converted to a DataFrame

Question four was looking for a DataFrame that included the counts of establishments with a hygiene score of zero for each Local Authority. This required the construction of a pipeline that included a match query for the hygiene score, a group query which counted the number of matches in each Local Authority, and a sort query which ordered the results from highest to lowest. The 55 results were then converted to a DataFrame.

