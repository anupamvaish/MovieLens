# MovieLens
Movie Lens Project


Project - MovieLens Data Analysis

The GroupLens Research Project is a research group in the Department of Computer Science and Engineering at the University of Minnesota. The data is widely used for collaborative filtering and other filtering solutions. However, we will be using this data to act as a means to demonstrate our skill in using Python to “play” with data.

Objective:
  To implement the techniques learnt as a part of the course.

Learning Outcomes:
  Exploratory Data Analysis
  Visualization using Python
  Pandas – groupby, merging

Domain
  Internet and Entertainment
Note that the project will need you to apply the concepts of groupby and merging extensively.

Datasets Information:

rating.csv: It contains information on ratings given by the users to a particular movie.
  user id: id assigned to every user
  movie id: id assigned to every movie
  rating: rating given by the user
  timestamp: Time recorded when the user gave a rating

movie.csv: File contains information related to the movies and their genre.
  movie id: id assigned to every movie
  movie title: Title of the movie
  release date: Date of release of the movie
  Action: Genre containing binary values (1 - for action 0 - not action)
  Adventure: Genre containing binary values (1 - for adventure 0 - not adventure)
  Animation: Genre containing binary values (1 - for animation 0 - not animation)
  Children’s: Genre containing binary values (1 - for children's 0 - not children's)
  Comedy: Genre containing binary values (1 - for comedy 0 - not comedy)
  Crime: Genre containing binary values (1 - for crime 0 - not crime)
  Documentary: Genre containing binary values (1 - for documentary 0 - not documentary)
  Drama: Genre containing binary values (1 - for drama 0 - not drama)
  Fantasy: Genre containing binary values (1 - for fantasy 0 - not fantasy)
  Film-Noir: Genre containing binary values (1 - for film-noir 0 - not film-noir)
  Horror: Genre containing binary values (1 - for horror 0 - not horror)
  Musical: Genre containing binary values (1 - for musical 0 - not musical)
  Mystery: Genre containing binary values (1 - for mystery 0 - not mystery)
  Romance: Genre containing binary values (1 - for romance 0 - not romance)
  Sci-Fi: Genre containing binary values (1 - for sci-fi 0 - not sci-fi)
  Thriller: Genre containing binary values (1 - for thriller 0 - not thriller)
  War: Genre containing binary values (1 - for war 0 - not war)
  Western: Genre containing binary values (1 - for western - not western)

user.csv: It contains information of the users who have rated the movies.
  user id: id assigned to every user
  age: Age of the user
  gender: Gender of the user
  occupation: Occupation of the user
  zip code: Zip code of the use
 
Please provide you insights wherever necessary.
1. Import the necessary packages - 2.5 marks
In [ ]:

​
2. Read the 3 datasets into dataframes - 2.5 marks
In [ ]:

​
3. Apply info, shape, describe, and find the number of missing values in the data - 5 marks
Note that you will need to do it for all the three datasets seperately
In [ ]:

​
4. Find the number of movies per genre using the item data - 2.5 marks
In [ ]:

​
5. Drop the movie where the genre is unknown - 2.5 marks
In [ ]:

​
6. Find the movies that have more than one genre - 5 marks
hint: use sum on the axis = 1
Display movie name, number of genres for the movie in dataframe
and also print(total number of movies which have more than one genres)
In [ ]:

​
7. Univariate plots of columns: 'rating', 'Age', 'release year', 'Gender' and 'Occupation' - 10 marks
HINT: Use distplot for age. Use lineplot or countplot for release year.
HINT: Plot percentages in y-axis and categories in x-axis for ratings, gender and occupation
HINT: Please refer to the below snippet to understand how to get to release year from release date. You can use str.split() as depicted below or you could convert it to pandas datetime format and extract year (.dt.year)
In [18]:

a = 'My*cat*is*brown'
print(a.split('*')[3])
​
#similarly, the release year needs to be taken out from release date
​
#also you can simply slice existing string to get the desired data, if we want to take out the colour of the cat
​
print(a[10:])
print(a[-5:])
brown
brown
brown
In [ ]:

​
8. Visualize how popularity of genres has changed over the years - 10 marks
Note that you need to use the percent of number of releases in a year as a parameter of popularity of a genre
Hint 1: You need to reach to a data frame where the release year is the index and the genre is the column names (one cell shows the number of release in a year in one genre) or vice versa. (Drop unnecessary column if there are any)
Hint 2: Find the total number of movies release in a year(use sum(axis=1) store that value in a new column as 'total'). Now divide the value of each genre in that year by total to get percentage number of release in a particular year. (df.div(df['total'], axis= 0) * 100)
Once that is achieved, you can either use univariate plots or can use the heatmap to visualise all the changes over the years in one go.
Hint 3: Use groupby on the relevant column and use sum() on the same to find out the number of releases in a year/genre.
In [ ]:

​
9. Find the top 25 movies according to average ratings such that each movie has number of ratings more than 100 - 10 marks
Hints :
Find the count of ratings and average ratings for every movie.
Slice the movies which have ratings more than 100.
Sort values according to average rating such that movie which highest rating is on top.
Select top 25 movies.
You will have to use the .merge() function to get the movie titles.
Note: This question will need you to research about groupby and apply your findings. You can find more on groupby on https://realpython.com/pandas-groupby/.
In [ ]:

​
10. See gender distribution across different genres check for the validity of the below statements - 10 marks
Men watch more drama than women
Women watch more Sci-Fi than men
Men watch more Romance than women
compare the percentages
Merge all the datasets
There is no need to conduct statistical tests around this. Just compare the percentages and comment on the validity of the above statements.
you might want ot use the .sum(), .div() function here.
Use number of ratings to validate the numbers. For example, if out of 4000 ratings received by women, 3000 are for drama, we will assume that 75% of the women watch drama.
