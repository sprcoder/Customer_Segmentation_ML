# Customer_Segmentation
 A machine learning project to predict which segment a customer/client would fall.
 
**Collecting Data:**
	An automobile company has plans to enter new markets with their existing products (P1, P2, P3, P4 and P5). After intensive market research, they’ve deduced that the behavior of new market is similar to their existing market.
 
In their existing market, the sales team has classified all customers into 4 segments (A, B, C, D). Then, they performed segmented outreach and communication for different segment of customers. This strategy has work exceptionally well for them. They plan to use the same strategy on new markets and have identified 2627 new potential customers.
 
Data is taken from Kaggle. https://www.kaggle.com/datasets/vetrirah/customer
 
**Preparing the Data:**
* Analyzed data and found issues with unrequired attributes that are not required for prediction such as ID field.  Removed unrelated attributes from the data to make the prediction more effective.
* Missing values in a field makes it irrelevant to determine the output making it less useful for training the model. Hence, removed data rows with missing values.
* Random Sampling: Increased the available data size in an unbiased manner, so the model is not affected by duplicate data's.
* Feature Scaling - Normalization: Used MinMaxScaler to normalize all numerical features to be in the range of [0, 1].
 
 
**Choosing a Model:**
Since the data has labelled outputs, it comes under supervised learning. But, we have implemented a hybrid model of combining unsupervised and supervised learning.
 
* First, A Clustering model is used to split the data set into different clusters. For this we have chosen K-Prototypes. It is a combination of K-Means and K-Modes. It is effective when having both categorical and numerical data. As in this case.
* Secondly, A Classification algorithm is used on each clustered data. We have chosen Decision Tree Classifier.
 
 
**Training the Model:**
* We are identifying the number of clusters required for the data using the Elbow Method.
* Each cluster is found to have class imbalance problem. That is resolved using Oversampling method.
* Each cluster is trained on a decision tree classifier.
 
 
**Evaluating the Model:**
Each cluster is validated and tested with the training data. The mean accuracy of all the cluster is approx. 72%
 
**Parameter Tuning:**
The hyperparameter tuning is important for Decision Trees as they are prone to result in overfitting problems. Hence, we are identifying the best parameters for a cluster(Gini/Entropy, Max_depth). This is implemented using GridSearchCV from sklearn.model_selection. This provides the best parameter for a cluster which can be used in a decision tree.
 
**Making Predictions:**
The resulting 72% accuracy is comparatively best as it is much better than the implementations found in Kaggle for the same dataset. We have achieved this by exploring the possibility of implementing a hybrid approach for this dataset.
