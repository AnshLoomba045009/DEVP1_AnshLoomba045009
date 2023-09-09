Project Objectives: 

•	General Description of Data 
•	Analysis : Basic Descriptive & Mathematical or Statistical Analysis
•	Findings & Inferences 
•	Managerial Insights 
•	Implications
       


Description of Data : 

The data collected by me was for the Sci-Fi movie segment on IMDb (https://www.imdb.com/search/title/?genres=sci-fi&), by designing a web scrapper I collected the data in the form a list and then converting the same into a dataframe.



 



This command shows you the first 5 rows of your dataframe. It helps you see that nothing looks weird and everything is ready for analysis.












Analysis, Findings & Inferences: 

 

1.	Time Period of Movies: The dataset covers movies released from 1927 to 2023, with an average release year of approximately 2004. This indicates that the dataset is fairly recent and includes movies from a broad historical range. 
2.	Runtime: The average movie runtime is about 105 minutes, with a minimum of 55 minutes and a maximum of 242 minutes. Most movies (75%) have runtimes between 92 and 114 minutes. 
3.	IMDb Ratings: The average IMDb rating is around 6.12, with a minimum rating of 1.5 and a maximum rating of 8.8. The ratings exhibit a moderate spread, indicating that movies vary in quality, but the average rating is slightly above average. 
4.	Metascore: The average Metascore is approximately 53.29, with scores ranging from 6 to 98. The Metascores tend to be lower on average compared to IMDb ratings, indicating potential differences in critical and audience reception. 
5.	Votes: The number of votes varies widely, with an average of approximately 138,081 votes. The dataset includes movies with as few as 34 votes and as many as 2,462,168 votes, suggesting a diverse set of movies in terms of popularity and audience engagement. 
6.	IMDb vs. Metascore Correlation: Further analysis is needed to determine the exact correlation coefficient between IMDb ratings and Metascores. A positive correlation would suggest that highly-rated movies on IMDb tend to receive higher Metascores from critics, while a negative correlation would indicate a disconnect between critical and audience opinions. 
7.	IMDb vs. Runtime Correlation: A correlation analysis can determine if there is a relationship between movie runtime and IMDb ratings. A positive correlation would suggest that longer movies tend to receive higher IMDb ratings, while a negative correlation would indicate the opposite. 
8.	Metascore vs. Runtime Correlation: A correlation analysis can also determine if there is a relationship between movie runtime and Metascores. A positive correlation would imply that longer movies tend to receive higher Metascores from critics, while a negative correlation would suggest the opposite. 
9.	Popularity vs. Ratings: Analyzing the correlation between the number of votes a movie receives and its IMDb rating or Metascore can reveal whether more popular movies tend to receive higher ratings or critical acclaim.



 


We can see that the strongest correlation is between the IMDB score and the metascore. This is not surprising since it's likely that two movie rating systems rate similarly.
The next strongest correlation we can see is between the IMDB rating and the number of votes. This is interesting because as the number of votes increases, you have a more representative sample of the population rating. It's strange to see that there is a weak association between the two, though.
The number of votes roughly increases as the runtime increases as well.
We can also see a slight negative association between IMDB or metascore and the year the movie came out. 

 

IMDB Ratings vs. the Number of Votes
The association above shows some outliers. Generally, we see a greater number of votes on movies that have an IMDB rating of 85 or more. There are fewer reviews on movies with a rating of 75 or less.


Another thing that might be an insight is to see is how many movies of each rating there are. This can show you where Sci-Fi tends to land in the ratings data.
 


We can see that there were a few movies rated as “Approved” and was curious what that was. You can filter down the dataframe with this code to drill down into that:

 


This revealed that most of these movies were made before the 80s






We could also check out if any years or decades outperformed others on reviews. I took the average metascore by year and plotted that with the following code to explore further 



# What are the average metascores by year?
final_df.groupby('year')['metascore'].mean().plot(kind='bar', figsize=(16,8), title="Avg. Metascore by Year", xlabel="Year", ylabel="Avg. Metascore")
plt.xticks(rotation=90)
plt.plot();

 


There is a gradual, mild decline as you progress through history in the average metascore variable. It seems that ratings have leveled out around 55-60 in the last couple decades. This might be because we have more data on newer movies or newer movies tend to get reviewed more.












final_df['year'].value_counts().plot(kind='bar', figsize=[20,9])

After running the above code we can see that the 1927 movie only had a sample of 1 review. That score is then biased and over-inflated. We can see that the more recent movies are better represented in reviews.
 


![image](https://github.com/AnshLoomba045009/anshloomba045009/assets/142685372/1f29ef59-e6c0-4871-a7f7-1edf4681ea6f)

