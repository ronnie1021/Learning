# System Desgin

## Basic Component of Entire System
1. Recommendation system
2. Log system
3. User behavior system
4. UI

## Design of Recommendation System
Abstract Design: user -> features (e.g. user's feature, similarity, item features) -> recommended items
Core task of Recommendation System
- how to get features of target users
- how to find items based on features

### Features of users:
- Demographic Features (anything from registration e.g. age, gender, nationality)
- Bahavior Features (e.g. what items are viewd, ratings)
- Topic Features (Find what topics user is interested in)

### System Design 
1. Multiple engines for each feature task (each engine represents one recommendation strategy) to generate inital recommendations
2. Filter, rank and explain recommendations 

- Pros: easy to delete and add engine for tryout of different strategy and based on user preference, 
adjust weights on results from each engine

### Engine Design
Three steps
1. Get user behavoir data and output user features
2. Combine features with feature-item similarity table with to initial recommendation items
3. Filter, fank, explain initial recommendation items

> Feature-item similarity table feature, item, weight. we can have multiple tables based on different user behavior

### Filtler 
- Filter those items that not meet specific business rules 
- User has interacted with 
- Low quality items

### Rank By
- Novelty, 
- Diversity, 
- Adaptivity in time (e.g. people see different recommended items every time) 
- User feedback (analyze results from users interactions with previous recommendations)


