# Evaluation of Recommender Systems

## What is a **good** recommender Systems
There are three important stakeholders of recommender systems:

1. Users
2. Content providers
3. Website providers

A good recommenders system should meet the needs of those three stakeholders 

## Experiment methods for evaluating the key metrics

### Offline Experiment (contains several steps):
1. Obtain user related data 
2. Fit data into model and get predictions(results)
3. use offline metrics to evaluate results from different models
  
- pros

  Experiment with differnet algorithms and models quickly without involving actual users
  Don't need support of acutal running system. Just user data is required
- cons

  Can't evaluate business metrics
  offline metrics is different from business metrics (e.g. accuracy(offline) vs customer satisfation(business))

### User Study
User studay fills the gap of what offline experiment cannot provide by sampling acutal users and ask them how they fell

- pros

  Can evaluate business metrics based on response from users
  easier to make modifications than system acutally going live
  
- cons

  High cost
  Hard to conduct in a large scale and so result is not statisically sound 
  Hard to find representative and not biased users
### Online Experiment

### A/B Testing

With A/B Testing , we can try different algorithms on different groups and compare different results for business metrics. 
But A/B Testing is a relatively huge topic. There are plenty of things need to consider before getting a valid result 
- pros
  
  Can fairly compare performance of diffrent algorithms on online(business) metrics (e.g. CTR)
  
- cons 
  
  How to design the entire system (make sure different A/B Testings do not interferes with each other)  
  how to effectively segment users (how to avoid bias)
  
To sum up, In order to make a new recommendation algorithm online, you have to take three steps:
1. Using offline experiment to prove it is better than current algorithm in terms of those offline metrics
2. Using user study to make sure it won't affect the user's satisfaction
3. Using A/B testing to make sure if those business metrics are better

## Recommendation System Properties 
  
### Prediction Accuracy (offline)
There are three categories of measuring prediction accuracy

#### Measuring Ratings Prediction Accuracy
it predicts users'rating on a specific item
metrics for measure is MAE or RMSE

#### Measuring Usage Prediction
In some cases, we don't care about users rating on specific items. Just predict items user may be intereseted in.
metrics for measure is Precision at N.  
> trade off between TPR and FPR, so we choose Precision
Use precision-recall curves or ROC curves (choose based on use case) 
while precision-recall curve emphasizes on proportion of items get recommended that are prefered , 
ROC curves emphasize on proportion of items not preferred but get recommended.

#### Measuring rankings of Prediction
In this case, we are not only interested in recommending items that user like, we also care about the ordering of those items
metrics NDPM(Normalized Distance-based Performance Measure)
use ratings to rank if explicit user ratings are available

### Coverage
#### Item Space Coverage
whether the systems covers the enough long tail products
To accurately mearsure the item space coverage, we need to count frequecy of each item appears in the recommendation.
In the information theroy, we can measure it by entropy or Gini index.

#### User Space Coverage
In many cases, not all users get recommendations (e.g. new users with no history and accurcay does not meet the threshold)

### Cold Start
It measures how system treats the new item added or new users

### Diversity
whether the items recommendted are different from each other.
Can be calculated by similarity between items

### Novelty
Recommend something that user has not seen before

### Serendipity
recommend something that does not matach user's history but user likes

### Confidence
System's confidence in its predictions. System could add probability of users preference towards the item.
There is a confidence bound added to each predicted score.
In the light of two algorithms with same prediction accuracy, we can choose them based on how close of those confidence bounds
towards the true value.

### Trust
Users' trust in the recommendation also plays important role. 
It may be beneficial to recommend something that user already liked so as to create credibility of the system.

### Adaptivity
Systm abiltiy to adapt to changes in customer behaviors, new items coming.
Rate by which system adapts to those changes

### Scalability
System is able to scale with the growth of the data

## Exploratory Data Analysis on Items and Users
Data related to Users and Items satisfies the Powerlaw Distribution, also called long tail distribution.
Sample data that meets the long tail distribution 
>  let **number of users has interactions with k items** be x, and **range of k items** be y

>  let **numbers of items has interactions with k users** be y, and **range of k users** be y 

Those two are all meet the long tail distribution
> Note: More active users tend to view less popular items and new users tend to view most popular items
