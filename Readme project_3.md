# Project 3: Fake News Detection Using Natural Language Processing (NLP) and Classification Modeling

## Distinguishing Between Subreddit Posts From the r/TheOnion & r/nottheonion

### Introduction & Problem Statement

a.Introduction

Reddit is an American social news aggregation, web content rating, and discussion website. Registered members submit content to the site such as links, text posts, images, and videos, which are then voted up or down by other members. Within each subreddit, there are text, image post, upvote or downvote posted by users to express their comments to the content of the post.

b.Problem statement

For this project, we select the subreddit that similiar on surface r/nottheonion and r/theonion. Subreddit r/nottheonion focus on true stories that are so mind-blowingly ridiculous that you could have sworn they were from The Onion while subreddit r/theonion foucs American satirical articles on international, national, and local news.

Due to the name of these 2 subreddits are highly appear to be misleading and confused. There will be problem for the moderator to maintain the subreddits. When performing maintenance, the moderator may accidentally deleted multiple posts from r/nottheonion and r/theonion. But, the moderator was not able to recover the titles of the lost posts.

Our goals of the project:

Using the natural language processing to build a classification model for

● training on posts submitted before 01 Jan 2022 to classify the recovered posts back to their respective subreddits, r/nottheonion and r/theonion, based solely on the post titles.

● as a proof of concept for the development of an automated moderator which would automatically delete posts that do not belong to the subreddit that they are posted to.

● Having automated moderators police the subreddit for spam posts would free up time for human moderators, who are volunteers, to do things that they want to do


### Summary 

We perform the text processing and cleaning using the technique  Make text lowercase, remove text in square brackets,remove links,remove punctuation,extra space and remove words containing numbers. Also,text processing carried out by using stop words to remove the commonly used word such as "the", 'a', 'an' etc. Also tokenisation is used to split a text object into smaller units while lemmanizsation is used to reduce the word to its root stem for example run, running, runs, runed derived from the same word as run. 

After the section of clearning, we proceed to EDA to analyse the Ngram, Top count and WordCloud.

And further, In the previous section, we have performed the text processing and cleaning from the dataset we scrapped from subreddits r/theonion and r/nottheonion. The next step we will proceed to the following steps:

Create a baseline model

1.To transform the data using vectorizers, Countvectorizer and TfidfVectorizer

2.Fit the model to train the datasets

3.Evaluate the models base on some evaliation matrics (Precision, ROC-AUC)

4.Select the best models and tune hyper-parameters

Countvectorizer and TfidfVectorizer are used to convert the text to a numeric form. Term Frequency Inverse Document Frequency (TFIDF) works by roportionally increasing the number of times a word appears in the document but is counterbalanced by the number of documents in which it is present. While Countvectorizeralso called Bag-of-Words which converts text into fixed-length vectors by counting how many times each word appears.

We will select a range of classification techniques to test including Logistic Regression,Random Forest and Support Vector Machine (SVM) classification.


### Conclusion


The most optimal model for detecting the fake news is using the logistic regression with CountVectorizer. The optimal parameters for this model are with ngram_range = (1,1) and alpha = 10.

*Accuracy: 68.8%

*ROC: 59.1%

*Train: 93.7%

*Test: 87.3%

Model sufficiently good to classify posts - 68.8% accuracy with almost 70% of lost data will be recovered correctly.

Limitation:

The major limitation of Logistic Regression is the assumption of linearity between the dependent variable and the independent variables. By using Logistic Regression, non-linear problems can’t be solved because it has a linear decision surface. Logistic Regression should not be used if the number of observations is lesser than the number of features, otherwise, it may lead to overfitting.

Recommendations:

● More data to train model

● Examine text more closely

* Remove words that do not provide additional information

● Engineer metadata as additional features

* Character count, word count, sentiment analysis etc
