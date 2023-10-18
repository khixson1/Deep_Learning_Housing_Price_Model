# Deep_Learning_Housing_Price_Model
Exploratory Data Analysis (EDA) using KMeans clustering to classify homes from attributes.  Principle Component Analysis (PCA) employed for dimensionality reduction followed by a sequential deep learning model designed to predict home price from home attribute data.

**<h2>A KMeans model was used to cluster the houses into an optimal number of clusters.</h2>**
An elbow plot and silhouette score were used to find the optimal number of clusters.

![elbow plot](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/c946f747-2de2-4074-bcd4-092528ad4da1)
![SilhouettePlot](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/8fdb4e71-e828-4d6f-9e2a-ded0e8618993)
The Elbow Plot suggests that an ideal number of clusters is between 4 and 10
The Silhouette Plot indicates that 5 is the ideal number of clusters. I will use 5 clusters as the silhouette coefficient was highest for n_clusters = 5.


![3D cluster plot](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/5a72f7b2-e302-4e3e-922b-3197bed441cc)
**First 3D Plot Visualization Interpretation:**

Cluster 0 primarily contains the homes that use a lot of brick/stone
Cluster 1 contains homes that have relatively lower sale prices and lower total living space
Cluster 2 contains homes that have the highest total living space
Cluster 3 contains homes that have a relatively moderate total living space with some brick/stone use
Cluster 4 contain homes that are relatively moderate in sale price and with a relatively smaller living space and no use of brick/stone
![3Dplot2](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/620d015e-eb55-45f4-ae4c-9a4cd577f6bc)
**Second 3D Plot Visualization Interpretation:**

Cluster 1 contains homes that have relatively lower sale prices and no or small basemet sizes
Cluster 2 contains homes that largely do not have basements and are newest
Cluster 3 contains homes that aer older and with more sizable basements
Cluster 4 contain homes that are least expensive, are relatively new, and which have a relatively large basement
![bargraphs](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/06a6e395-237f-47f0-8e38-2e7862eb7f10)
**Bar Graph Visualization Interpretation:**

Cluster 0: Contains homes with brick/stone, relatively high sale price, older, low number of bedrooms and bathrooms
Cluster 1: Contains homes that are older, with the smallest square footage, the least expensive, and relatively few bedrooms and bathrooms
Cluster 2: Contains homes that are the most expensive, are relatively new, have the larges total living space and largest upper floor, smallest basement square footage, largest attached garages, largest open porches, small enclosed porches, small decks, and a large number of bedrooms and bathrooms
Cluster 3: Contain homes that were build mid-century, has relatively more bedrooms and bathrooms than that other homes, has relatively larger decks, have the largest basements, largest daylight basements, largest garage basements, and the largest first floors
Cluster 4: Contain the newest homes, the smallest first floors, the largest upper floors, have a high number of 3qtr bathrooms, have large decks and enclosed porches, and have relatively large daylight basements

**<h2>Three sequential models were employed with the goal of predicting housing price from metadata of house attributes</h2>**
**Sequential Model #1: One hidden layers with 95 nodes in the 1st and only**
![model1](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/2141976f-77af-4dd1-8df3-0547b0bb22b6)

**Sequential Model #2: Two hidden layers with 95 nodes in the 1st layer and 15 nodes in the second layer with 500 epochs.**
![model2](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/7c87db4c-468a-47e6-ae81-cd6e47a180b8)

**Sequential Model #3: Two hidden layers with 95 nodes in the 1st layer, 15 in the second layer, with drop out regularization between runs and employing EarlyStopping, with only 200 epochs.**
![model3](https://github.com/khixson1/Deep_Learning_Housing_Price_Model/assets/8357088/b2d92877-2f16-43b7-a102-98214acdee9b)

Of the three test models, model #3 performed the best as it was the fastest model, is not too terribly overfit and uses drop out to help minimize overfitting. However, model #3 was not very accurate in it's prediction. The R2 was around 60% and the RMSE shows that predictions can be off by over $160K which means that more work could be done to refine the model in order to improve the accuracy.



