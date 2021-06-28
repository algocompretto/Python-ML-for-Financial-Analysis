# Machine Learning in Finances

## Customer Segmentation
Customer segmentation is the subdivision of a market into discrete customer groups that share similar characteristics. It can be a powerful tool to identify unsatisfied customer needs. Mostly, customer is segmented in four greater groups:
1. Demographic information, such as gender, age, marital status, income, education and occupation.
2. Geographical information, which differs depending on the scope of the company. It can be specific towns or countries, or a customer's city, state and country of residence.
3. Psychographics, such as social class, lifestyle and personality traits.
4. Behavioral data, such as spending and consuming habits, product/services usage, and desired benefits.

Our motivation in this customer segmentation process is to take advantage of this to:
- Determine appropriate product pricing
- Develop customized marketing campaigns
- Design an optimal distribution strategy
- Choose specific product features for deployment
- Prioritize new product development efforts

### What is K-Means algorithm?
Clustering is a machine learning technique that involves grouping similar data points together, it is a unsupervised learning method commonly used. Our goal is to separate the data into K distinct non-overlapping subgroups (clusters) of equal variance, minimizing a criterion known as the inertia - or within-cluster sum-of-squares.
KMeans works in baby steps:
1. Pick number of clusters (Not sure which number to choose? Check "The Elbow Method" section)
2. Initialize the center points of the cluster (centroids) by shuffling the dataset and then selecting K data points for the centroids
3. Assign data points to the cluster with the nearest centroid
4. Recompute centroid position by taking the mean of all data points assigned to the cluster
5. Steps 3 and 4 are repeated until centroids aren't moving much between iterations anymore

It is an easy to implement algorithm that is also fast, with complexity of O(k * n * T) where n is the number of samples, and T is the number of iteration. The disadvantage is that KMeans doesn't put data points that are far away from each other into the same cluster, even when they obviously should be. In this case the DBSCAN (Density-based spatial clustering of applications with noise) algorithm performs the best.

### The Elbow Method
The Elbow Method shows us what can be the ideal number of clusters based on the sum of squared distances between data points and their assigned cluster's centroid. We pick k at the spot where the SSE starts to flatten out, which looks like an elbow.
![Elbow Method graphic](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia.geeksforgeeks.org%2Fwp-content%2Fuploads%2F20190606105746%2Finertia.png&f=1&nofb=1)

### Autoencoding


### Principal Component Analysis (PCA)

