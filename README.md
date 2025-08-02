COMPANY: CODTECH IT SOLUTIONS

NAME: SAHANA

INTERN ID: CT04DZ1200

DOMAIN: MACHINE LEARNING

DURATION: 4 WEEKS

MENTOR: NEELA SANTOSH

##DESCRIPTION OF THE TASK 4: RECOMMENDATION SYSTEM

This recommendation system is built using user-based collaborative filtering—a method that predicts a user's preferences by analyzing the preferences of similar users. It begins with importing necessary Python libraries such as pandas, numpy, cosine_similarity from sklearn, and mean_squared_error from sklearn.metrics, along with the sqrt function from Python's math module. These libraries provide essential tools for data manipulation, similarity measurement, and evaluation of prediction accuracy.

The first step involves creating a dataset representing user-item ratings. This dataset is structured as a list of dictionaries, where each entry includes a user ID (User), an item ID (Item), and the rating the user has given to the item (Rating). This is transformed into a pandas DataFrame to facilitate easy manipulation. The ratings represent user preferences and serve as the input for constructing a recommendation system.

Next, a user-item matrix is constructed using the pivot function. This matrix has users as rows and items as columns, with the corresponding cell values representing the ratings each user has given to each item. If a user has not rated a specific item, the corresponding cell remains empty (NaN). This matrix is the core structure upon which similarity computations and rating predictions are performed.

To compute similarities between users, the missing ratings (NaN) are filled with zeros to ensure that the cosine similarity function can be applied without error. Cosine similarity measures the cosine of the angle between two vectors—in this case, user rating vectors. The result is a square similarity matrix where both rows and columns represent users, and each value represents how similar two users are in terms of their item ratings. A value closer to 1 implies high similarity, while a value near 0 indicates little to no similarity.

The code then defines a function named predict_ratings that takes in a target user ID, the original user-item ratings matrix, and the computed similarity matrix. It identifies which items the target user has not rated yet and attempts to predict these ratings. For each unrated item, the function calculates a weighted average of ratings from other users who have rated that item. The weight is the similarity between the target user and the other users. The higher the similarity, the more influence that user’s rating has on the prediction. This technique assumes that users who have similar rating behaviors in the past are likely to share preferences in the future. If no similar users have rated the item, the prediction is marked as NaN.

After defining the prediction logic, the code proceeds to recommend items to a specific user, U4. The system first identifies the items U4 has not rated and then applies the prediction function to estimate what rating U4 would give to those items. These predicted ratings are then sorted in descending order to highlight the most relevant recommendations. In this case, items I1 and I4 are predicted for U4 with ratings of 5.0 and 3.0 respectively. These values are based on the preferences of users similar to U4.

An optional evaluation phase follows the recommendation process. To assess the accuracy of the predicted ratings, a test set is simulated by specifying a known user-item pair and its actual rating. In this example, it's assumed that user U4 rated item I1 as 3.0. The code then predicts the rating for the same pair using the previously defined logic. The predicted rating is compared to the actual rating using the Root Mean Square Error (RMSE) metric. RMSE is commonly used to evaluate prediction models, with lower values indicating better accuracy. Here, the predicted rating was 5.0 while the actual rating was 3.0, resulting in an RMSE of 2.0. This suggests there is some deviation between predicted and actual preferences, highlighting the challenge of modeling human behavior perfectly.

The modules and methods used are essential for implementing collaborative filtering. pandas is used for data loading, transformation, and matrix operations; numpy supports numerical operations; sklearn.metrics.pairwise.cosine_similarity is vital for finding similar users based on their rating vectors; and mean_squared_error helps evaluate the predictive performance. The cosine similarity method is particularly suitable for this type of sparse data, where many users have not rated all items.

This recommendation system, although built on a small dataset, demonstrates the core concept of collaborative filtering, which is widely used in real-world applications. Platforms such as Netflix, Amazon, and Spotify employ similar techniques to suggest movies, products, or songs based on user behavior and preferences. This system can be scaled and enhanced by incorporating matrix factorization techniques, integrating more complex similarity measures, or switching to item-based filtering if user-based similarity is not effective.

Overall, this project showcases a simple yet effective approach to building a recommendation engine. It covers data representation, similarity computation, prediction of unknown ratings, and performance evaluation. Such systems are crucial in modern digital environments, where personalization significantly enhances user engagement and satisfaction. The deliverable aligns well with typical academic or industry requirements, presenting both functionality and evaluation in a clear and interpretable manner.

##OUTPUT

<img width="936" height="887" alt="Image" src="https://github.com/user-attachments/assets/b4d9fc39-1de7-4b42-bfc6-585d8d3213de" />
