![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Redis: Querying the Movies Dataset

## Objective

This lab will help you practice querying data in Redis using the dataset provided [here](https://redis.io/learn/howtos/moviesdatabase/import#importing-the-movies-theaters-and-users). You will execute a series of progressively challenging queries to retrieve, filter, and manipulate movie-related data.

## Dataset Overview

The dataset consists of the following key types:
- **Movies**: Stored as hashes with keys like `movie:<id>`
- **Theaters**: Stored as hashes with keys like `theater:<id>`
- **Users**: Stored as hashes with keys like `user:<id>`
- **Ratings**: Stored as sorted sets to track movie ratings
- **Indexes**: Secondary indexes to facilitate searching

## Lab Instructions

**Perform the following queries in Redis CLI.**

### **1. Retrieve a Movie by ID**

Fetch details of the movie with ID `1`.
```sh
HGETALL movie:1
```

### **2. List All Movies**

Retrieve all movie IDs stored in Redis.
```sh
KEYS movie:*
```

<br>

**Redis CLI does not support some of the operations bellow. You must try them out in Python.**
- [A Quick Guide Here](https://medium.com/@tubelwj/redis-simplified-a-concise-tutorial-on-redis-with-python-c449194ecf07) 

### **3. Find Movies by Title Prefix**

Find all movies that start with "The Lord of the Rings".

```python
import redis

r = redis.Redis()
results = []

for key in r.scan_iter(match="movie:*"):
    title = r.hget(key, "title").decode('utf-8')
    if "The Lord of the Rings" in title:
        results.append(title)
```

### **4. Retrieve Theaters in a Specific City**

Find all theaters located in "New York".

### **5. Get Top-Rated Movies**

Retrieve the top 5 movies based on rating.

### **6. Find Movies Released After 2010**

Retrieve movies where the release year is greater than 2010.

### **7. Get Movies by Genre**

Find all movies labeled as "Action".

### **8. Get Movies with Ratings Between 7 and 9**

Find all movies that have a rating between 7.0 and 9.0.

## **Completion**

After executing these queries, you should have a strong understanding of how to interact with Redis and retrieve relevant movie data efficiently. Try modifying the queries to experiment further!

## **Additional Challenges**

- Modify query #5 to return the top 10 rated movies.
- Find the 3 most recent movies added to the dataset.

**Happy querying!** :rocket: