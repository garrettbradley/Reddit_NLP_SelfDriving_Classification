# Self-Driving Market Assessment 

# Text Classification & Sentiment Analysis using NLP on Reddit Posts and Comments


## Problem Statement

Explore various subreddit communities to identify potential self-driving car buyers in order to conduct upcoming marketing campaign.  Specifically, what subreddits besides r/selfdrivingcars may provide a good customer base for targeted marketing?  To answer this question I built a classification model that uses natural language processing (NLP) to classify user posts & comments from multiple subreddit groups, and conducted Sentiment Analysis on this data to gain insights on users perceptions towards self-driving cars.  

This project was branded with Tesla as a usecase, but it can be applied to any automotive company currently developing selfdriving capabilities.  The methodology can also be replicated for other online communities or social platforms to determine optimal marketing targets. 

Beyond the self-driving car marketing use case, the project is important because it can provide a general gauge or pulse-check of public sentiment towards the concept of a future self-driving society.  This public perception gauge can help inform policy makers with respect to pushing or halting legislation surrounding self-driving cars.


## Executive Summary

Reddit pushshift API was used to scrape user posts and comments from four subreddits including: r/selfdrivingcars, r/futurology, r/technology. 5000 data points were collected on the most recent posts and comments for a total of 10,000 records for each subreddit from 2018 to the present.  This data was used for training the classification models.  In addition, 500 data posts and 500 comments were collected for each subreddit, for each year of its existence.  r/Technology began in 2012, while r/Futurology and r/selfdrivingcars began in 2011 and 2012 respectively.  This data was used exclusively for Sentiment Analysis.

In conducting this project, an initial assumption was made that r/selfdrivingcars would have neutral or positive sentiment, owing to its name. As such this group served as the control, or baseline from which to compare the others, both in the classification problem and in sentiment analysis. With this assumption, r/selfdrivingcars is a natural starting place for a target advertising group.  One drawback of this group, however, is that it only has 51.4k members.  This is not a sufficiently sized advertising target.  Thus, we considered the other two subreddits, r/Futurology and r/Technology, with 14.2 million and 8. 2 million members respectively, as alternative marketing targets of sufficient size.

Three classification models were tested on a combined dataset of r/selfdrivingcars and r/futurology submission posts.  These included Logistic Regression, Support Vector Machine, and Random Forest.  All three performed roughly the same in accuracy at 89%, and all three were somewhat overfit, with SVM being the least overfit.  Logistic Regression and Support Vector Machine were also tested on classifying Comments data from a combined set from r/selfdrivingcars and r/futurology.  Both models again performed roughly the same at 83% accuracy. SVM was again the least overfit of the models, 

Sentiment Analysis was conducted on both Submission posts and Comments for each of the three subreddit groups, for each year of the subreddit's existence.  As seen in plots below, sentiment analysis showed r/selfdrivingcars had relatively high sentiment across all years of existence, with the exception of 2018, which was due to the death of a pedestrian from an Uber self-driving car collision.  Sentiment for r/Technology was the lowest of the three across its lifespan, and sentiment for r/Futurology was positive for the majority of its existence with the exception of 2018 as an outlier.

#### Sentiment Analysis for r/selfdriving cars
[Mean Annual Sentiment for Submssions in r/selfdrivingcars](https://git.generalassemb.ly/garbradafork/project_3/blob/master/plots/sent_sdc_subs.png)

[Mean Annual Sentiment for Comments in r/selfdrivingcars](https://git.generalassemb.ly/garbradafork/project_3/blob/master/plots/sent_sdc_coms.png)

#### Sentiment Analysis for r/Technology
[Mean Annual Sentiment for Submssions in r/technology](https://git.generalassemb.ly/garbradafork/project_3/blob/master/plots/sent_tech_subs.png)

[Mean Annual Sentiment for Comments in r/technology](https://git.generalassemb.ly/garbradafork/project_3/blob/master/plots/sent_tech_coms.png)

#### Sentiment Analysis for r/Futurology
[Mean Annual Sentiment for Submssions in r/futurology](https://git.generalassemb.ly/garbradafork/project_3/blob/master/plots/sent_fut_subs.png)

[Mean Annual Sentiment for Comments in r/futurology](https://git.generalassemb.ly/garbradafork/project_3/blob/master/plots/sent_fut_coms.png)


## Conclusions & Recommendations

From the classification problme, we learned that classification models performed generally well at classifying text data between two groups that have some overlap of contextual content.  The classification data was not filtered by any search terms, thus we expected that the models should be able to classify relatively well, with any misclassifications due to the overlap of content regarding 'self-driving cars', or outlier data of very few words lacking context.  We also learned that Comment text is a more challenging classification problem than is Submission text data.  This was also to expected, considering the increase in variation of content, word, and sentence length that occurs in within organic dialoague, as is present in Comment forums.  Submission posts on the other hand, are typically shorter, more direct towards a certain topic, and often consist of a news headline.

Sentiment Analysis revealed that Futurology had significantly higher sentiment across its lifespan than that of Technology subreddit group.  This indicates the users in this group generally have a more positive perception of self-driving cars, which is somewhat to be expected considering most are interested in future society. With its positive sentiment and its size of 14.2 Million users, we can conclude that among the subreddits groups analyzed, r/Futurology provideas a good customer base alongside the smaller r/selfdrivingcars group, for a targeted marketing campaign on self-driving cars.  The lower sentiment r/technology group, and other communities with low sentiment, should not be ignored entirely, but rather approached with a different marketing strategy.  This strategy should be one in which the goal is provide positive opinion influence rather than generate direct sales.
