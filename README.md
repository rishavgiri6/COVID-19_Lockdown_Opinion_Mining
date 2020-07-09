# COVID-19_Lockdown_Opinion_Mining

             IBM Hack Challenge 2020

Topic-
 SENTIMENT ANALYSIS OF COVID-19 TWEETS -visualization DASHBOARD

Team Name: Curiosity
Team Members:

RISHAV GIRI, Department of Computer Science, Heritage Institute of Technology (Autonomous), Kolkata, West Bengal, India, rishavgiri.work@gmail.com
SIDDHANT CHAKRABORTY, Department of Computer Science, Heritage Institute of Technology (Autonomous), Kolkata, West Bengal, India, 
siddjamescarter@gmail.com
SARASIJ JANA Department of Computer Science, Heritage Institute of Technology (Autonomous), Kolkata, West Bengal, sarasij190@gmail.com
SAYAN SEAL, Department of Computer Science, Heritage Institute of Technology (Autonomous), Kolkata, West Bengal, India, sayan1863@gmail.com




 CCS Concepts: Deep Learning            Natural Language Processing              Tweet Analysis 
Additional keywords and phrases: Covid-19, Computational Linguistics, Data Visualization, Sentiment Analysis

                                              
  

       INDEX
                                                                                       Pages

1. General Description/ Abstract                                                        3

2. Novelty/Uniqueness                                                                   4

3. Technology Stack                                                                     5

4. Methodology and Algorithms                                                           6-12

5. Findings                                                                            12-16
 
6. Socio-economic/business implications                                                16-20

7. Future scope of work                                                                 21

8. Conclusion                                                                           21







1. General Description/Abstract:

Coronavirus disease (COVID-19) is an infectious disease caused by a newly discovered coronavirus.
As of 5th June 2020, the coronavirus COVID-19 is affecting 213 countries and territories around the world and 2 international conveyances. :
 
 
Most people infected with the COVID-19 virus will experience mild to moderate respiratory illness and recover without requiring special treatment. Older people, and those with underlying medical problems like cardiovascular disease, diabetes, chronic respiratory disease, and cancer are more likely to develop serious illness.
The best way to prevent and slow down transmission is be well informed about the COVID-19 virus, the disease it causes and how it spreads. We must protect ourselves and others from infection by washing your hands or using an alcohol based rub frequently and not touching your face. 
The virus spreads primarily through droplets of saliva or discharge from the nose when an infected person coughs or sneezes, so it’s important that we also practice respiratory etiquette (for example, by coughing into a flexed elbow).
This endangers our physical health indeed, but alongside, social distancing also poses a threat to our emotional stability. Thus, it is crucial to understand public sentiments under COVID-19.
We deployed Sentiment Analysis on tweets and Topic Modelling on news to aid the understanding of sentiment trends. Based on these, as a part of our hackathon, we utilized web scraping techniques to collect data from multi-platforms, leveraged NLP techniques to process the text data, analyzed the data by sentiment analysis alongside topic Modelling, and built visualization dashboards as a daily sentiment monitor product to present the results.
2. Novelty/Uniqueness
The Corona Virus endangers our physical health indeed, but alongside, social distancing also poses a threat to our emotional stability. Thus, it is crucial to understand public sentiments under COVID-19.
The novelty of our endeavor lies in the fact that we analyzed the sentiments of COVID-19-related tweets in several ways, and have come up with exclusive insights as our findings. The overall trend shows that the public has been more optimistic over time. Digging into the multi-dimensional sentiment analysis, we found that the sentiment “Assertive” went up, and “Fearful” went down through the time. Besides, the Sentiment Density indicates that the public turned out to be less loaded with emotions. At last, the topics behind the sentiments unfolded more intriguing details, which have all been highlighted below.
To fight the coronavirus not only needs the guidance from the government but also a positive attitude from the public. Our analysis provides a potential approach to reveal the public’s sentiment status and help institutions respond timely to it.

Who will benefit by our analysis
•	Twitter: As a social media, Twitter takes the responsibility to control negative rumors spreading during this period for the social good. Twitter can monitor the sentiment trends and study the abnormal emotion peaks like what we did.
•	Medical Institutions: Our analysis can help medical institutions know the emotion changes during the COVID-19. Doctors can provide help to people who potential have mental health problem.
•	Business Owners: Keeping a watchful eye on trending topics and people’s emotion change can help business owners run marketing campaign appropriately and find out potential business opportunities, such as new services that needed by people.
The dataset can be used for
•	The study of people's interactions on Twitter during COVID-19 period
•	The study of public media's behavior during COVID-19 period
•	The study of people's emotion change during COVID-19 period
•	More NLP data mining with plenty tweets during such specific period
3. Technology Stack

DATA SOURCES:
Confirmed Cases:
1.	Time series data of confirmed cases: Johns Hopkins CSSE (daily data from 01/16 to 05/02)
Twitter:
1.	Tweets on Twitter retrieved with TwitterScraper API (daily data from 01/20 to 04/26)
Note: the daily data is a sample from each day's tweets, not the population. We sampled out abough 13K tweets for each day, 1.3M in total.
2.	Twitter trending topics retrieved by scraping Trendogate.com (daily data from 01/20 to 04/11)
3.	Number of tweets with #COVID-19 shared by Tweet Binder
News:
1.	#COVID-19 news scraped from Fox News (daily data from 01/20 to 04/26)
2.	#COVID-19 news scraped from CNN (daily data from 01/20 to 04/26)


TOOLS:

1.	We utilized TextBlob, a popular NLP library, to conduct sentiment analysis by generating polarity score (negative [-1 ~ +1] positive) and subjectivity score (objective [0 ~ 1] subjective). Examples:
a.	'Great!' Polarity = 1
b.	'This is the worst situation.' Polarity = -1
c.	'It's raining.' Subjectivity = 0
d.	'I love the rain!' Subjectivity = 1

2.	We choose to use IBM's Tone Analyzer (a cloud service) to do the sentiment anlysis because it can provide 5 different tones of the text data which is more than positive-negative sentiment analysis.
3.	We used these data as training set for the Google BERT model, a state-of-art machine learning technique for classification. 
4.	LDA topic Modelling technique was used to summarise the news articles we scraped.
5.	Mallet, a natural language processing toolkit, was utilized to perform Latent Dirichlet Allocation (LDA) topical modelling

4. Methodology and Algorithms



Analysis Process



To study public sentiments, we chose Twitter as our target field. As one of the world’s biggest social network platforms, Twitter hosts abundant user-generated posts, which closely reflect the public’s reactions towards this pandemic with low latency. By deploying Natural Language Processing (NLP) methods on it, we were able to extract and quantify the public sentiments over time. The tools we used are TextBlob, IBM Watson Tone Analyzer, BERT, and Mallet.
At first, we used TextBlob to explore public sentiments, which showed an upward trend in being steadily more positive.
 
		       The process to generate 5 types of sentiments.




Then we dove in to analyze the sentiments on a more detailed level, in a multi-dimensional way, to reveal the trend more comprehensively. We used the IBM Watson Tone analyzer along with manual tags to label the sampled tweets with 5 sentiments and then built a classification model with BERT to classify all the tweets with 5 sentiments. With this, we were able to: 1) identify subtler sentiments in a tweet; 2) define a metric Sentiment Density, which could represent the complexity of the tweets’ sentiment.

 



To further understand the trend of sentiments, we decided to introduce news topic modelling with Mallet to add a layer of context for the sentiments. By building a dashboard comparing the sentiments of each topic, we could be more specific in understanding the trends.



Data Source
The two major data sources used for this analysis are Tweets and News from Jan 20th to Apr 26th on a daily basis. We also obtained statistics of confirmed cases from Johns Hopkins CSSE to complement the context of sentiments and topics. 



An Overall Look: What Happened on Twitter

Since the first confirmed case was reported in January 2020, #COVID-19 and other similar tags have been trending on Twitter. With 1.3M+ COVID-19 related tweets (about 10,000+ per day) collected, we wondered how people on Twitter reacted to such tweets over time. Firstly, we explored some engagement metrics of tweets, such as the number of likes. The figure below shows the average likes/replies/retweets per tweet on each day:
 
	Average likes/replies/retweets per tweet over time. For some days with unusually high numbers, we retrieved the tweet content who received the most likes/replies/retweets
From the chart, we can tell that people reacted to some #COVID-19 tweets hotly on several days from January to March (e.g. Jan. 29th, Feb. 26th, and Mar. 9th). The content of the tweets which received the most likes/replies/retweets changed from corona beer and COVID-19 in China to COVID-19 in the US and government’s actions. During late March and April, the average likes/replies/retweets per tweet tended to flatten, which indicates people on Twitter reacted or engaged in COVID-19 tweets less than they did previously.
Twitter is not only a place for people to respond to others’ tweets but also a platform to post your tweets and share your feelings. Thus, besides likes/replies/retweets, we also mined the content of COVID-19 related tweets to see how people’s feelings and expressions changed over time. With the help of TextBlob, a sentiment analysis library in Python, we extracted how subjective/objective (subjectivity) the content is and whether the content is positive or negative (polarity) for each tweet. 




 
How subjectivity (objective [0–1] subjective) and polarity (negative [-1 — +1] positive) of COVID-19  related tweets change over time is given in our diagrams in th repo. The dash lines represent the simple linear regression for average subjectivity and average polarity

According to our provided charts, with the development of COVID-19, the related tweets’ expression became more subjective (from about 0.33 to about 0.35) on average, and people’s feelings became more positive (from about 0.04 to about 0.06) on average. Why did this happen? Why with more and more people being infected with Coronavirus, the sentiment of related tweets went positive? With such questions, we went deep into what actual emotions the tweets reflected and what kinds of topics people talked about when mentioning this disease.







Further Analysis: Extract Multi-dimensional Sentiments
We conducted further analysis by utilizing the BERT model. BERT is Google’s pre-trained model that can be fine-tuned for a wide range of NLP tasks (learn more). Here in our case, it was used in combination with IBM’s Watson Tone Analyzer (learn more) to label the tweets with 5 sentiment types. Here is how we generated them:
Step one: We prepared a training dataset for the model to learn from, where we leveraged Watson Tone Analyzer to label each tweet with 5 sentiments. How the data looks like:
 
Examples of how the tweets were labelled
Step two: After that, we introduced the BERT Base uncased model and performed fine-tuning. Our implementation was heavily inspired by Chris McCormick. A binary classification model was built under each sentiment type and was then used to produce 1/0 tags for unlabeled tweets. Below are the five sentiment categories we extracted and typical tweets under them.
 
Typical tweets and their sentiments.
Step three: With the labels in place, we defined some metrics to help further comprehend the changes in the public sentiment. We first came up with a metric called Sentiment Level using the proportion of tweets with a certain sentiment to the total tweets on a day. Since one tweet can possess more than one sentiment, we also computed the Sentiment Density to show that on average how many different sentiments a tweet had on a single day. This figure will give us a direct impression of how much the tweets were “packed with” different emotions on a day. We then computed the day-on-day change of these metrics and formed the delta metrics. Below is a table to summarize our metrics.
 
Metrics definitions and formulas
5. Findings
After putting our model results back to the timeline under the pandemic context (we used the growth rate of the accumulated number of confirmed cases to reflect the spread of the disease), we summarized some interesting findings.

 




● Before the first confirmed case in the U.S. was reported (Jan 21st), sentiment “Analytical” was detected most in tweets, other Sentiment Levels remained low.
● Right after the first case reported, mixed sentiments arose, which indicates increasing social awareness of the pandemic.
● “Sad” is volatile but remains relatively high after it went up in January.
● In late February, different sentiments tended to diverge, “Assertive” increased, “Fearful” went down. Overloaded with information seems to have made people less sensitive.

Sentiment Density:

 
 

● Through the general trend of Sentiment Density in the above dashboard, we can infer that from late February till mid-March, people were undergoing the densest sentiments, especially in terms of the negative feelings, followed by the period of late January to mid-February.
● In April, the Sentiment Density decreased and stayed in a lower position, but it was still higher than that of the beginning.
What We Talk About When We Talk About COVID-19:
After studying the general trend of sentiments during the researched period, we wanted to add another layer of information to dissect the overall trend. We intended to extract some hot topics that people discussed when talking about COVID-19 and how the polarity (positive/negative) changed under each topic, so we firstly extracted several topics from the COVID-19 related news and then leveraged the keywords in those topics to classify tweets.
The advantage of using news texts for topic modelling instead of tweets is that tweets are short, informal, and highly sentimental, which are hard to process for topic models, while news texts would capture the important events under COVID-19 in a formal and neutral way.

6. Socio-Economic/Business Impact

Extracted News Topics


 
We utilized Mallet, a natural language processing toolkit, to perform Latent Dirichlet Allocation (LDA) topical Modelling[2], and summarized 8 topics. We named these topics by summarizing the topic keywords returned by the model, and they are as follows (following the descending sequence of frequency): Life during COVID-19, Covid-19 in China, Lockdown Order, Medical Tests & Analysis, Government Actions, Game Season, Economy Impact, Medical Supply. Equipping with the TextBlob’s sentiment analysis, the trending of these topics over time are as follows:
Different topics cover different periods, and most resonate with the fact. For example, before March, only a few topics like COVID-19 in China appeared in coronavirus-related news. After March, owing to the widespread of COVID-19, the number of related news began surging, especially for topics like Medical Tests. One interesting finding is that, with the execution of lockdown order since mid-March, the news about Life during COVID-19 peaked as the majority of news with the highest average polarity score.
For the sentiment of these topics in news, the topic Life during COVID-19 is undoubtedly the most positive as well as the most objective topic among all the topics, followed by the band containing Game Season, Medical Supply and Medical Tests and Analysis. However, the topic COVID-19 in China, on the other hand, got the most negative and subjective wordings.





News Topics in Tweets
 


With the topics summarized by the news topic modelling, we used corresponding keywords to classify tweets. After filtering tweets by keywords (described in the chart), suggested by the 8 topics, and the topic trends are shown below:
The same trend of news topics applies here as the trend of tweets mentioning COVID-19 in China peaked before March and began decreasing since the first case in the US. As shown in the graph, the public paid more and more attention to government actions over time. Medical-related, economic impact, and life during COVID topics increased slowly. As for the game season, mask, and stay at home topics did not show an obvious upward trend over time.
 
 
 

 
When analyzing the sentiments, we can see an increasing positivity in most topics.
● The topic that has the highest positivity is still about Life during COVID-19. And one trend that has the fastest positivity growth rate is the sentiment about stay at home, which echoes the point brought above that people are getting less sensitive during the quarantine.
● For the debating topic about the facial mask and the stay at home, we can see the polarity went down first at the beginning of the COVID-19 outbreak but went up later during March.
● The tweets talking about government-related issues tended to have a very fluctuant sentiment trend line, and the polarity went down on the whole.
● Recently, more and more tweets talking about economic impacts, such as layoffs and unemployment, but the overall sentiments trend towards positive.
● For the game season, many games were cancelled due to the Coronavirus, so the sentiment of those tweets was not very positive.
● Lastly, the tweets mentioning ‘China’ became more negative over time.


6. Future Scope of Work
Our analysis has shown some relationships between confirmed cases’ growth and the trends of sentiments. With more granular data such as geographic data, demographic information, and so on, further insights can be generated, such as public sentiment monitoring the hardest-hit areas. With a more specific target, the analysis would be more valuable for institutions or governments to take action.
Limitations
Besides the IBM's service limitation, since evaluating a text tone is not an objective thing, the sentiment analysis we conducted is impacted by our subjectivity and the accuracy of IBM Tone Analyzer.



7. References:
[1] McCormick, Chris, and Nick Ryan. 2019. “BERT Fine-Tuning Tutorial With  Pytorch · Chris Mccormick”. Mccormickml.Com. https://mccormickml.com/2019/07/22/BERT-fine-tuning/.
[2] Prabhakaran, Selva. 2018. “Topic Modelling With Gensim (Python)”. Machine Learning Plus. https://www.machinelearningplus.com/nlp/topic-Modelling-gensim-python/.

[3] Working demonstration of IBM Watson Tone Analyzer- https://www.ibm.com/watson/services/tone-analyzer/

[4] Topic modelling with Mallet NLP Toolkit- https://programminghistorian.org/en/lessons/topic-Modelling-and-mallet
