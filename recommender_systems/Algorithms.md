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
