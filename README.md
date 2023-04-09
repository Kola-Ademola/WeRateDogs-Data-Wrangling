# WeRateDogs Twitter Account Dataset Analysis
## by Kola Ademola
<img src="images/weratedogs.webp" alt="weratedogs" width="1024"></br>
___
## INTRODUCTION
___
This project is purely for the sake of improving my **Data Wrangling & Data Cleaning Skills**, I did alot of cleaning and wrangling on this dataset, it really helped sharpened my data assesment skills for quality issues.
___
## DATA SOURCING
___

For this project I got my data from multiple sources(twitter api & downloaded tsv file online).  
The data contains info on the tweets gotten from the @WeRateDogs twitter account about dogs and their ratings. This data has alot of quality issues which you'll be seeing how I solved or wrangled the data making it clean and ready for my analysis.

* I started by downloading the dataset necessary for this project both programmatically and directly
from the web;  
___TWITTER ARCHIVE DATASET___
![](images/twitter_archive_df.png)
___IMAGE PREDICTIONS DATASET___
![](images/image_pred_df.png)
* And then I also scraped data using the twitter API.
![](images/tweet_api1.png)
___SCRAPED TWEETS USING THE TWITTER API___
![](images/tweet_api2.png)
___
## SKILLS DEMONSTRATED & DATA TRANSFORMATION
___
After downloading and loading my datasets, I moved on to importing the necessary librabries needed for wrangling and cleaning the data.
___LIBRARIES USED___
![](images/libs.png)
I visually assessing and programmatically assessing the data and right off the bat I spotted some Quality issues in the twitter_archive and image_predictions
dataset. 
## The Quality issues I spotted are as follows:

1. Drop the columns with too many null values
(in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_st
atus_user_id, retweeted_status_timestamp) as they won’t be neccesary

2. Missing values represented as "None" instead of "NaN" in
the twitter_archive dataset

3. timestamp & retweeted_status_timestamp as object instead of datetime in
the twitter_archive dataset

4. in_reply_to_status_id, retweeted_status_id, retweeted_user_id & in_reply_to_u
ser_id as float instead of int in the twitter_archive dataset

5. The source column should be of type category instead of object in
the twitter_archive dataset

6. The source column needs to be sliced to get the actual source of the tweet rather
than the whole HTML

7. The ratin_numerator & rating_denominator has values outside the 15/10 rating
standard

8. We don't need the exact time of the tweet in the twitter_archive dataset, the date is
okay

9. We have predicions of False and we need just True values since it’s for dogs in
the image_predictions dataset

10. Inconsistent dog type name predictions in the image_predictions dataset


## Here are the Tidiness issues I spotted after assessing the data also:

1. The dog categories should be a categorical variable in a single column rather than 4
columns in the twitter_archive dataset

2. Retweeted posts not needed for this projected, should be deleted from
the twitter_archive dataset

3. We need just 2 tables ie One with the whole tweet info
(joining twitter_archive & tweet_info on tweet_id) and the second table should be
the image predictions


### After spotting all the above issues with the datasets I moved on to use the following steps in
cleaning the data and getting it ready for analysis

* I made a copy of all the datasets first.
Then for the Quality issues I:

* This columns(in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retwe
eted_status_user_id, retweeted_status_timestamp) won’t be necessary for this
project and coupled with having too many null values they need to be dropped

* I'll be replacing the "None" with NaN so it can be used properly during analysis or
further cleaning in the twitter_archive dataset


# Insights:

* There's a strong positive correlation between the number of likes and retweets but we musnt take this as causality.

* The tweets from iPhone seem to get most likes & retweets but this can also be due to the fact that most of the tweets were from iPhones.

* The dog with the higher ratings had more retweets and likes from my analysis but we should take into account of those with the rating of 15 as they were having very low likes and retweets also.
