# Different Algorithms for Offline Experiment

## Collaborative Filtering
This Algorithm only based on users bahavior(transaction, online log) data.
> This is very basic and popular algorithm based on nearest neighbors.
### Metric for evaluation
1. Recall
2. Precision
3. Coverage
4. Novelty 

### Item-Based Collaborative Filtering vs User-Based Collaborative Filtering
#### For Item Based
1. We first calculate the similarity between items based on users'data
> Basic Method: every user plays equal role in determining item similarities
> Improved Method: IUF(Inverse User Frequence) less Frequent users play more important role
> Normalize items similarity matrix by its maximum value will improve accuracy
> Explanation: Suppose there are two categories A and B, items within A has similarity of 0.6, and 0.5 within B
if users got same number items within A and B and we don't normalize it, we would get recommended items from B all the time.
Normally, most puplar items has higher similarity within them. so normalizing it improves coverage.
2. Find k nearest item towards the item user act on
3. Recommend items based on target user's previous behavoirs

#### For User Based
1. similarity calculation between users 
> Basic method: Cosine similarity
> Improved method:User-IIF (penalize effects of popular items)
2. Find k nearest neighbors of target user
3. Recommend items based on weighted average those neighbors 
But user-based collaborative filtering is not widely adopted. 
because normally user base is bigger than item and difference of users' preference is large   

> User based recommendations emphasize on interests of a group of users, while item based recommendations emphasize on 
personal preference. 
> Computationally, User based needs more computing power than item based.
> Item based is more suitable when there are more long tail products.
> Item based is based on user's past preference, which is more likely to earn credibility. 
> Item based is fast in terms of more Adaptivity, and fast reponse to cold start problem

## Latent factor Model (Similar to SVD)
Idea behind is trying to cluster users' interest through latent factor. and then recommend product
in their clusters.
1. To cluster items
2. Identify which cluster of items user more likely to be intereseted in. and quantify interests
3. To a specific cluster, identify items in the cluster to recommend and also weight those items


