# EIGA: Movie Recommendation system

## 1. INTRODUCTION AND DESCRIPTION

The goal of this project is to develop a movie recommendation system based on recommendation algorithms that personalize the user's movie choices. These algorithms use the user's profile and past behavior to generate personalized recommendations. Popular examples of recommendation systems include Amazon, Netflix, and YouTube. These systems help users find and select items from a vast collection of items available on the internet or other electronic information sources. By analyzing a user's needs and preferences, these systems present a small selection of items that are well-suited to the user. There are several approaches commonly used in recommendation algorithms, including collaborative filtering, content-based filtering, and hybrid methods.
This project focuses on Movie recommendation.

Recommendation algorithms mainly follow following approaches: 

-	**Content-based filtering**: One approach used in recommendation systems is content-based filtering. This approach suggests similar items based on the metadata of a particular item. For example, in a movie recommendation system, this approach would use metadata such as genre, director, description, actors, etc. to make recommendations. By analyzing the metadata of the items a user has shown interest in, the system can recommend other similar items that the user may enjoy. This approach can be effective in making personalized recommendations, as it takes into account the specific interests and preferences of the user. 

-	**Collaborative filtering**: Another approach used in recommendation systems is collaborative filtering. This approach matches users with similar interests and provides recommendations based on this matching. Unlike content-based filtering, which uses item metadata to make recommendations, collaborative filtering does not require item metadata. Instead, it relies on the ratings and preferences of users to make recommendations. For example, if two users have similar ratings for a set of movies, the system may recommend the same movies to both users. This approach can be effective in making personalized recommendations because it takes into account the specific interests and preferences of individual users. However, it may not be as effective in recommending new or unfamiliar items, as it relies on the ratings and preferences of other users.

-	**Demographic**: A third approach commonly used in recommendation systems is the use of popularity or genre-based recommendations. This approach offers generalized recommendations to all users, based on the popularity or genre of the items. For example, a movie recommendation system may recommend the most popular movies or the most popular movies in a particular genre to all users. This approach is simple and easy to implement, as it does not require the use of complex algorithms or user data. However, it may not be as effective in making personalized recommendations, as it does not take into account the specific interests and preferences of individual users.

-	**Knowledge-based**: It suggests products based on inferences about user’s needs and preferences, item selection and its basis for recommendation.

-	**Hybrid**: It is the one that combines multiple recommendation techniques together to produce the output. If one compares hybrid
recommender systems with collaborative or content-based systems, the recommendation accuracy is usually higher in hybrid system. 

## 2. APPLICATION ARCHITECTURE

![image](https://user-images.githubusercontent.com/56411093/181216896-3366c2e7-0853-465d-b5dd-c93490da25df.png)

## 3. METHODOLOGY:

### Dataset Generation:

Scrapping using beautiful soup from imdb website that shows list of films year wise, used **Beautiful Soup** library in python and passed the url of IMDB website that sorted movies based on of number of votes over years 1991-2022.

[Collaborative-filerting dataset](https://www.kaggle.com/rounakbanik/the-movies-dataset?select=ratings_small.csv)

[Sentiment-analysis dataset](https://www.kaggle.com/datasets/columbine/imdb-dataset-sentiment-analysis-in-csv-format)

### Content Based filtering:
This engine computes similarity between movies based on certain metrics and suggests movies that are most similar to a particular movie that a user liked. The metrics used here are:
- **Movie descriotion**.
- **Director name, Cast and Genre**.

To calculate a similarity between two movies **Cosine Similarity** is used

Used the TF-IDF Vectorizer, so calculating the Dot Product will directly gives the Cosine Similarity Score. 
Therefore, sklearn's linear_kernel was used instead of cosine_similarities since it is much faster.


#### Limitations
-	It is not capable of capturing tastes and providing recommendations across genres.
-	It doesn't capture the personal tastes and biases of a user. 
-	Anyone querying our engine for recommendations based on a movie will receive the same recommendations for that movie, regardless of who s/he is.

These limitations are overcame by 

### Collaborative filtering
It is of 2 types:

- **User based filtering**-  This system recommends products to a user that **similar users have liked**. For measuring the similarity between two users we can either use pearson correlation or cosine similarity. 
One main issue is that users’ preference can change over time. It indicates that precomputing the matrix based on their neighboring users may lead to bad performance. To tackle this problem, we can apply item-based CF.

- **Item Based Collaborative Filtering**- This recommends items based on their similarity with the items that the target user rated. 
Likewise, the similarity can be computed with Pearson Correlation or Cosine Similarity.
The major difference is that, in this, we fill in the blank vertically, as oppose to the horizontal manner that user-based CF does.

## 4. Results

![image](https://user-images.githubusercontent.com/56411093/181223016-53cb44d8-f488-4963-a6c5-d2d42746fb31.png)
![image](https://user-images.githubusercontent.com/56411093/181223030-ae1c2d3d-e67b-43ed-b4d0-65f214fc51ba.png)

In content-based filtering, the system uses the characteristics of a particular item (in this case, a movie) to recommend other similar items. In the example given, the system was able to identify "The Dark Knight" as a Batman movie and recommended other Batman movies based on factors such as the cast, crew, director, and genre.

Collaborative filtering, on the other hand, uses the preferences and behaviors of other users to make recommendations. In the example given, a user who liked "The Dark Knight" would likely be recommended other movies by the same director, Christopher Nolan, as these would be personalized to their tastes.

Overall, it appears that collaborative filtering provides better recommendations than content-based filtering, as it takes into account the individual preferences of users.

To improve the recommendations, the system was modified to only recommend movies that are popular and have received positive critical response. This was done by removing movies with low ratings and only considering the top 25 movies with the highest similarity scores. A weighted rating was then calculated for each movie using IMDB's formula. This approach provides a more refined list of recommendations, as it eliminates poor-quality movies.

![image](https://user-images.githubusercontent.com/56411093/181223271-a0d342c1-a379-4755-9bed-023afbd1399d.png)

 

### Sentiment-analysis: 
The model is trained on IMDB movie reviews dataset on kaggle. Used 3  approacehs Linear SVC , MultinomialDB and nueral network.
NN model performed better.

 ![image](https://user-images.githubusercontent.com/56411093/181221143-79e3dd27-1a4b-4b4d-8673-823136c841aa.png)

 
## 5. LIVE LINK
https://tinyurl.com/eiga-by-swetangi

## 6. SCREENSHOTS
![image](https://user-images.githubusercontent.com/56411093/181219781-4ad85be2-6c56-42df-b38a-810f38d3e6cf.png)
![image](https://user-images.githubusercontent.com/56411093/181219891-3a3f7fac-16ee-4874-9f95-77374bffe8f0.png)
![image](https://user-images.githubusercontent.com/56411093/181219908-dc3b3b36-3740-480c-a9e4-bccb6dd26b89.png)
![image](https://user-images.githubusercontent.com/56411093/181219930-9a45ea22-7862-4365-9f5b-71f7646b523e.png)
![image](https://user-images.githubusercontent.com/56411093/181219949-3fa1932a-b146-46c5-9f15-c56a018daf28.png)



