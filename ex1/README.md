Summary
=======

This dataset (ml-latest-small) describes 5-star rating and free-text tagging activity from [MovieLens](http://movielens.org), a movie recommendation service. It contains 100836 ratings and 3683 tag applications across 9742 movies. These data were created by 610 users between March 29, 1996 and September 24, 2018. This dataset was generated on September 26, 2018.

Users were selected at random for inclusion. All selected users had rated at least 20 movies. No demographic information is included. Each user is represented by an id, and no other information is provided.

The data are contained in the files `links.csv`, `movies.csv`, `ratings.csv` and `tags.csv`. More details about the contents and use of all these files follows.

This is a *development* dataset. As such, it may change over time and is not an appropriate dataset for shared research results. See available *benchmark* datasets if that is your intent.

This and other GroupLens data sets are publicly available for download at <http://grouplens.org/datasets/>.


Usage License
=============

Neither the University of Minnesota nor any of the researchers involved can guarantee the correctness of the data, its suitability for any particular purpose, or the validity of results based on the use of the data set. The data set may be used for any research purposes under the following conditions:

* The user may not state or imply any endorsement from the University of Minnesota or the GroupLens Research Group.
* The user must acknowledge the use of the data set in publications resulting from the use of the data set (see below for citation information).
* The user may redistribute the data set, including transformations, so long as it is distributed under these same license conditions.
* The user may not use this information for any commercial or revenue-bearing purposes without first obtaining permission from a faculty member of the GroupLens Research Project at the University of Minnesota.
* The executable software scripts are provided "as is" without warranty of any kind, either expressed or implied, including, but not limited to, the implied warranties of merchantability and fitness for a particular purpose. The entire risk as to the quality and performance of them is with you. Should the program prove defective, you assume the cost of all necessary servicing, repair or correction.

In no event shall the University of Minnesota, its affiliates or employees be liable to you for any damages arising out of the use or inability to use these programs (including but not limited to loss of data or data being rendered inaccurate).

If you have any further questions or comments, please email <grouplens-info@umn.edu>


Citation
========

To acknowledge use of the dataset in publications, please cite the following paper:

> F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets: History and Context. ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19. <https://doi.org/10.1145/2827872>


Further Information About GroupLens
===================================

GroupLens is a research group in the Department of Computer Science and Engineering at the University of Minnesota. Since its inception in 1992, GroupLens's research projects have explored a variety of fields including:

* recommender systems
* online communities
* mobile and ubiquitious technologies
* digital libraries
* local geographic information systems

GroupLens Research operates a movie recommender based on collaborative filtering, MovieLens, which is the source of these data. We encourage you to visit <http://movielens.org> to try it out! If you have exciting ideas for experimental work to conduct on MovieLens, send us an email at <grouplens-info@cs.umn.edu> - we are always interested in working with external collaborators.


Content and Use of Files
========================

Formatting and Encoding
-----------------------

The dataset files are written as [comma-separated values](http://en.wikipedia.org/wiki/Comma-separated_values) files with a single header row. Columns that contain commas (`,`) are escaped using double-quotes (`"`). These files are encoded as UTF-8. If accented characters in movie titles or tag values (e.g. Misérables, Les (1995)) display incorrectly, make sure that any program reading the data, such as a text editor, terminal, or script, is configured for UTF-8.


User Ids
--------

MovieLens users were selected at random for inclusion. Their ids have been anonymized. User ids are consistent between `ratings.csv` and `tags.csv` (i.e., the same id refers to the same user across the two files).


Movie Ids
---------

Only movies with at least one rating or tag are included in the dataset. These movie ids are consistent with those used on the MovieLens web site (e.g., id `1` corresponds to the URL <https://movielens.org/movies/1>). Movie ids are consistent between `ratings.csv`, `tags.csv`, `movies.csv`, and `links.csv` (i.e., the same id refers to the same movie across these four data files).


Ratings Data File Structure (ratings.csv)
-----------------------------------------

All ratings are contained in the file `ratings.csv`. Each line of this file after the header row represents one rating of one movie by one user, and has the following format:

    userId,movieId,rating,timestamp

The lines within this file are ordered first by userId, then, within user, by movieId.

Ratings are made on a 5-star scale, with half-star increments (0.5 stars - 5.0 stars).

Timestamps represent seconds since midnight Coordinated Universal Time (UTC) of January 1, 1970.


Tags Data File Structure (tags.csv)
-----------------------------------

All tags are contained in the file `tags.csv`. Each line of this file after the header row represents one tag applied to one movie by one user, and has the following format:

    userId,movieId,tag,timestamp

The lines within this file are ordered first by userId, then, within user, by movieId.

Tags are user-generated metadata about movies. Each tag is typically a single word or short phrase. The meaning, value, and purpose of a particular tag is determined by each user.

Timestamps represent seconds since midnight Coordinated Universal Time (UTC) of January 1, 1970.


Movies Data File Structure (movies.csv)
---------------------------------------

Movie information is contained in the file `movies.csv`. Each line of this file after the header row represents one movie, and has the following format:

    movieId,title,genres

Movie titles are entered manually or imported from <https://www.themoviedb.org/>, and include the year of release in parentheses. Errors and inconsistencies may exist in these titles.

Genres are a pipe-separated list, and are selected from the following:

* Action
* Adventure
* Animation
* Children's
* Comedy
* Crime
* Documentary
* Drama
* Fantasy
* Film-Noir
* Horror
* Musical
* Mystery
* Romance
* Sci-Fi
* Thriller
* War
* Western
* (no genres listed)


Links Data File Structure (links.csv)
---------------------------------------

Identifiers that can be used to link to other sources of movie data are contained in the file `links.csv`. Each line of this file after the header row represents one movie, and has the following format:

    movieId,imdbId,tmdbId

movieId is an identifier for movies used by <https://movielens.org>. E.g., the movie Toy Story has the link <https://movielens.org/movies/1>.

imdbId is an identifier for movies used by <http://www.imdb.com>. E.g., the movie Toy Story has the link <http://www.imdb.com/title/tt0114709/>.

tmdbId is an identifier for movies used by <https://www.themoviedb.org>. E.g., the movie Toy Story has the link <https://www.themoviedb.org/movie/862>.

Use of the resources listed above is subject to the terms of each provider.


Cross-Validation
----------------

Prior versions of the MovieLens dataset included either pre-computed cross-folds or scripts to perform this computation. We no longer bundle either of these features with the dataset, since most modern toolkits provide this as a built-in feature. If you wish to learn about standard approaches to cross-fold computation in the context of recommender systems evaluation, see [LensKit](http://lenskit.org) for tools, documentation, and open-source code examples.


Self-Practice Exercise – MovieLens
Database & EDA

In this exercise, you will practice the full data workflow using ONLY the tools demonstrated
in the lecture notebook: NumPy, Pandas, MySQL (via SQLAlchemy), Matplotlib/Seaborn, and
Automated EDA packages. You will download a public dataset (MovieLens), save it into a
local MySQL database, retrieve it with Pandas, and perform both manual and automatic
exploratory data analysis (EDA).

Dataset
We will use the MovieLens dataset (public ZIP archive).
Download: http://files.grouplens.org/datasets/movielens/ml-latest-small.zip
Contained files:
- ratings.csv → columns: userId, movieId, rating, timestamp
- movies.csv → columns: movieId, title, genres

Step 1 – Download & Extract the ZIP
Download and preview the dataset using Pandas (directly extract from the ZIP file):
```python
import pandas as pd
import requests
from zipfile import ZipFile
from io import BytesIO
url = 'http://files.grouplens.org/datasets/movielens/ml-latest-small.zip'
r = requests.get(url)
z = ZipFile(BytesIO(r.content))
ratings = pd.read_csv(z.open('ml-latest-small/ratings.csv'))
movies = pd.read_csv(z.open('ml-latest-small/movies.csv'))
ratings.head()
movies.head()
```

#PRE MYSQL
I have already running mysql server on
docker run --name my-mysql \
  -p 3306:3306 \
  -e MYSQL_ROOT_PASSWORD=232323 \
  -d mysql:8.0 \
  --default-authentication-plugin=mysql_native_password
# PRE conda
Required packages: pip install pandas numpy matplotlib seaborn sqlalchemy mysql-connector-python ydata-profiling sweetviz dtale requests

Step 2 – Save to MySQL
1. Create a new database:
```sql
CREATE DATABASE movielens;
USE movielens;
```

2. Create tables:
```sql
CREATE TABLE ratings (
userId INT,
movieId INT,
rating FLOAT,
timestamp BIGINT
);
CREATE TABLE movies (
movieId INT,
title VARCHAR(255),
genres VARCHAR(255)
);
```
3. Insert using Pandas + SQLAlchemy:
```python
from sqlalchemy import create_engine
engine =
create_engine('mysql+mysqlconnector://user:password@localhost:3306/movielens')
ratings.to_sql('ratings', engine, if_exists='replace', index=False)
movies.to_sql('movies', engine, if_exists='replace', index=False)
```

Step 3 – Query Back into Pandas
Retrieve the data from MySQL into a DataFrame:
```python
ratings = pd.read_sql('SELECT * FROM ratings', engine)
movies = pd.read_sql('SELECT * FROM movies', engine)
```

Step 4 – Manual EDA
Perform EDA using Pandas, Matplotlib, and Seaborn:
- Inspect structure with `info()` and `describe()`
- Join ratings with movies
- Top 10 movies by average rating (with minimum number of ratings)
- Histogram of ratings distribution
- Average rating per genre (expand genre column if needed)
- Scatterplot of rating count vs average rating

Step 5 – Automatic EDA
Repeat the analysis using an **automatic EDA package** shown in the notebook (e.g.,
pandas_profiling or sweetviz).
- Generate a profile report for the ratings and movies data
- Compare automated insights with your manual EDA findings

Tasks
1. Download and extract the ZIP, then inspect the first 5 rows of ratings and movies.
2. Create the movielens database and load the data into MySQL.
3. Query back into Pandas and confirm row counts match.
4. Perform MANUAL EDA:
- Top 10 highest-rated movies (with at least 20 ratings)
- Average rating by genre
- Histogram of ratings
- Scatterplot of rating count vs average rating
5. Perform AUTOMATIC EDA:
- Generate an automated EDA report
- Compare automated vs manual findings
