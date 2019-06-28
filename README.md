# Movie-Recommendation-System
Use Alternating Least Squares (ALS) with Spark for movie rating prediction

* We are using the MovieLens dataset to build up a movie recommendation system. It has veen collected by the GroupLens Research Project at the University of Minnesota. The MoviewLens dataset can be dowloaded [here](https://grouplens.org/datasets/movielens/latest/). 

There are two dataset, describing 5-star rating and free-text tagging activity from [MovieLens](https://movielens.org/), a movie recommendation service.  one is with 100,836 ratings and 3,683 tag, which is relatively small, and easy for us to test firstly and debug code. These data were created by 610 users between March 29, 1996 and September 24, 2018. This dataset was generated on September 26, 2018.

> ratings.csv (userId, moviewId, rating, timestamp)
> tags.csv (userId, moviewId, rating, timestamp)
> movie.csv (movieId, title, genres)
> links.csv (movieId, imdbId, tmdbId)

The full dataset includes 27753444 ratings and 1108997 tag applications across 58098 movies, we can use it for further analysis. These data were created by 283228 users between January 09, 1995 and September 26, 2018. This dataset was generated on September 26, 2018.

> ratings.csv (userId, moviewId, rating, timestamp)
> tags.csv (userId, moviewId, rating, timestamp)
> movie.csv (movieId, title, genres)
> links.csv (movieId, imdbId, tmdbId)
> Tag Genome (genome-scores.csv and genome-tags.csv) (movieId, tagId, relevance) (tagId, tag)

* Instead of just using dataset from MovieLens, we can also load [netflix data](http://academictorrents.com/details/9b13183dc4d60676b773c9e2cd6de5e5542cee9a) for testing.

### Work
* Achieved basic data ETL on MoviesLens samples, using Spark SQl and Data Frame.

* Spark SQL and OLAP
> get the number of users
> get the number of movies
> get the number of movies getting rated
> list unrated movies
> list movie genres
> list movie for each category (genre)

* Implemented ALS algorithm by applying ``Spark.MLlib`` package, which is an RDD-based API, to build the model and predict the ratings. The ALS algorithm is kind of collaborative filtering (item-item) model.

* Trained ALS model and tuned hyperparameters (number of iterations, regression parameter, ranks) by grid search to get the best model among canndidates.

* Plot the learning rate variation of validation annd training error for different iteration (1, 2, 5, 10).

* Tested model robustness on testing data and get the rmse error.

* Using the optimal recommendation system, calculate the similarity between each two movies and that of specific user and movie, giving recommendations for each user who rated movie.
