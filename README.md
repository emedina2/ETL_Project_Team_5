# ETL_Project_Team_5
 ETL Project

Goal : Finding Movie Musicals & their Data

Sources:
Musicals sales data
https://www.the-numbers.com/box-office-records/worldwide/all-movies/genres/musical 

Movie Database Info
http://www.omdbapi.com/

Kaggle Dataset for Streaming Services
https://www.kaggle.com/ruchi798/movies-on-netflix-prime-video-hulu-and-disney

Project Outline: 
Data Manipulation will be used to compare movie Musical data from the-numbers.com to find information regarding all movie musicals available. We will then cross reference the movies with a database that shows which movies are available for streaming.


Part 1: Utilizing Musical Sales Data & Streaming Service Dataset 

Extract
The Musical Sales Data & Streaming Service Dataset were added to a Resources folder as CSV’s, which were then imported to a Jupyter Notebook using Python / Pandas for transformation.

Transform
Once both datasets were loaded into the Jupyter Notebook, they were merged together by Movie Name to create a master table with all applicable data. 

From there, I created two additional datasets by copying and filtering the master table. Those two additional datasets are:
Streamable_Info: A view on which musicals are available for streaming on Netflix, Hulu, Amazon Prime, and Disney+. This was created by copying from the master table the movie name, year, and the streaming service it was available on. 
Musical_Info: A view on musical information, including the Director, Language, Genre, and Length. This was created by copying from the master table. 

Load
Data was loaded to PGAdmin Database where SQL can be used to further query the data. 


Part 2: Utilizing the OMDB API to pull Musical Movie Information

Extract
The data extracted from the Musical Sales Data site was used to compare Movie Titles in the Movie Database using an API call; the movies that matched available titles in the OMDB were then added to a dataframe, along with information related to the matching titles(Director, Actors, & Metascore).

Transform
	The dataframe created from the data extracted from the OMDB was then copied to a csv to allow for the information to be pulled without needing to perform another API call.
Using the Streaming Platforms CSV Emily was able to pull, we were able to then join the Musical Movie Titles that were matched in the OMDB with the Steaming Platforms data as one larger dataframe, but only joining on titles that were available for streaming.

Load
All the CSV files were converted back to a DataFrame using Pandas, then into a PostgreSQL Database for further analysis.
