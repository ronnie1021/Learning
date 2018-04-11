# Cold Start
There are three categories of Cold Start
1. User cold start
2. Item cold start
3. System cold start

Generally, There are several solutions for the cold start
## For user cold start problem
### Provide most popular recommendations instead of personalized recommendation
This is a easy solution, just recommend most popular items
### Take advantage of users' registration information
- Demographic information
- Classify User based on their Demographic information
### Obtain User interesets
- give users items to select what they are interested.
> those items need to be Most popular ones, have distinct categories with each other and have wide coverage of all catergores
- Social network data by linking social network account
## For item cold start problem
### use item meta data   
- Construct item vectors and cosine similarity. Problems: when meta data is limited
- LDA(latent Dirichlet Allocation) topic Model to identify topics. then use topic to calculated similarity



# User Generated Items
Clean tags before using them such clear synonym, stop words e.g
## User tags
User tags contain a lot of important information about their interests. 

We can try to give recommendation based on tags users give on items
## Recommendation based on tags
1. find what is most frequent tags user uses
2. find items that are labled most by those tags

For user cold start,
for new users, there won't be a lot of tags. To increase accuracy, we can add similar tags to users'tag
> Calculate similarity of tags is similar to calculate item 

> if two tags frequently being tage to one item, we consider it to be similar


## Recommendation of tags intead of items
- Reasons
  - It helps user to tag automatically 
  - Unify the words that user may tag a item
- Methods
  - Recommend most popular tags
  - Recommend popular tags based on item user has interacted with
  - Recommend user's popular tags
  - combin previous two with some weights



# Use Context Information 
- What is context information?
  - Time
  - Location
  - other background info (e.g. )
  
## Time
- Why do we need to think about time
  - User's interest changes over time
  - Item has its own lifetime
  - Seasonailty
  
### Time Dimension in Recommendation Systems
Several things to consider:
- System related time dimension
  - Average life span of items (consider item online when at one user interacts with it) vs average popularity of item 
  - Frequecy of users to website
  - System grows or shrinks?
- Real time recommendations (based instant user behavior)
### How incorporate time in Algorithms
- Item Based Collaborative Filtering  
  - Recommend items that are similar to items user lately interacted on 
  - Two items will be more similar if time interval of interaction on them is shorted 
- User Based Collaborative Filtering
  - Shorter time interval plays more important role when calculating neighbors
  - Use most recent behavior of user neighbors
- Graph model based on time

## Location
Location is critical, for example, user from same place tend to have similar behavior
Classify items and users both into two categories: one with location, one without

### How to incorporate time in Algorithms
Three types of Data set  
- (user, user location, item, ratings)


LARS (Treats location as different node in Tree sturcture, use ItemCF calculate recommendation sets on node, and parent node)

Find a way to linearly combine those recommendations

- (user, item, item location, ratings)

Calcuate normal ItemCF and use travelpenalty(which distance between item location and previous item location) 

- (user, user location, item, item location, ratings)

make sure user and recommended item are close

## Social Network Data

