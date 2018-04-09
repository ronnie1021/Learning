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

