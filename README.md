# Text-classification-Sentiment-Analysis-using-BERT
Using DistilBertTokenizer, TFDistilBertModel, SentenceTransformer, RandomForestClassifier

# Amazon Fine Food Reviews Analysis

Data Source: https://www.kaggle.com/snap/amazon-fine-food-reviews <br>
EDA: https://nycdatascience.com/blog/student-works/amazon-fine-foods-visualization/

The Amazon Fine Food Reviews dataset consists of reviews of fine foods from Amazon.<br>

Number of reviews: 568,454<br>
Number of users: 256,059<br>
Number of products: 74,258<br>
Timespan: Oct 1999 - Oct 2012<br>
Number of Attributes/Columns in data: 10 

<b> Attribute Information:</b>
1. Id
2. ProductId - unique identifier for the product
3. UserId - unqiue identifier for the user
4. ProfileName
5. HelpfulnessNumerator - number of users who found the review helpful
6. HelpfulnessDenominator - number of users who indicated whether they found the review helpful or not
7. Score - rating between 1 and 5
8. Time - timestamp for the review
9. Summary - brief summary of the review
10. Text - text of the review


#### Project Objective:
Given a review, determine whether the review is positive (rating of 4 or 5) or negative (rating of 1 or 2).
<br>
[Q] How to determine if a review is positive or negative?<br>
<br> 
[Ans] We could use Score/Rating. A rating of 4 or 5 can be considered as a positive review. A rating of 1 or 2 can be considered as negative one. A review of rating 3 is considered neutral and such reviews are ignored from our analysis. This is an approximate and proxy way of determining the polarity (positivity/negativity) of a review.

We analyze the review text(analyze the Sentiment) with various NLP technique to predict the score/rating. 

####  NLP Objective :
1) Perform Sentiment Analysis: Utilize diverse tokenization techniques, fine-tune pretrained BERT models, and employ various machine learning models for sentiment analysis on text data.

2) Evaluate and Address Challenges: Evaluate model performance, including handling imbalanced datasets, and assess both standard and advanced tokenization approaches.

3) Practical Applicability: Investigate the real-world applicability of advanced tokenization methods in NLP tasks.

<b> Approach followed: </b> <br/>
 We first performed datacleaning on the review text . Next we split the dataset to train, cv and test. Then we vectorize <br/>
 <h4>We vectorize text data in 3 ways </h4>

* SET 1 - TFIdf Tokenized         
* SET 2 - Sentence Transformer Tokenized      
* SET 3 - DistilBertTokenizer Tokenized    

1) We trained SET 1 and SET 2 on KNN Kd-Tree which serves as a baseline model
2) We trained SET 2 on RandomForestClassifier
3) We trained SET 3 on TFDistilBertModel
4) Finally we compare the performance of all the models

<b> 1. Baseline Model with TF-IDF: </b>

We used TF-IDF tokenized data and trained it with the K-Nearest Neighbors (KNN) KDTree model. This established a strong baseline for our analysis.

<b> 2. Sentence Transformer Tokenization: </b>

Building upon the baseline, we employed Sentence Transformer Tokenization and trained the tokenized data with both RandomForest (RF) and K-Nearest Neighbors (KNN) KDTree models. This allowed us to explore the performance of more advanced tokenization techniques and machine learning models.

<b> 3. BERT-Tokenized and Fine-Tuned Data: </b>

For a more advanced approach, we leveraged BERT-tokenized data, fine-tuned it using a pretrained DistilBERT model, and conducted a comprehensive evaluation of its performance. This represented the most sophisticated aspect of our analysis.

<b> 4. Model Training and Evaluation:  </b>

We meticulously trained our models using the respective tokenized datasets and assessed their performance on unseen test data. This comprehensive evaluation process included the calculation of various metrics to gauge the models' effectiveness.

<b> 5. Outstanding RandomForest Model:  </b>

Our evaluation revealed that the RandomForest (RF) model with SentenceTransformer tokenized data achieved an exceptional AUC score of approximately 99%. This remarkable performance underscores its suitability for the task at hand, particularly when dealing with imbalanced data.

NOTE: AUC is a crucial metric in such scenarios as it assesses the model's ability to accurately classify positive and negative instances, providing a more comprehensive measure of performance in situations where class distribution is skewed.
