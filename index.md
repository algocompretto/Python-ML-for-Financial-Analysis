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
Autoencoders are some kind of neural network that is used to learn feature representation in an unsupervised manner. It uses the same data for input and output. As shown in the figure, by adding a bottleneck in the network, it forces the network to create a compressed version of the input data, which is how it works, meanwhile, the decoder reconstructs the original input:
![Autoencoder](https://miro.medium.com/max/3110/0*uq2_ZipB9TqI9G_k)

### Principal Component Analysis (PCA)
Simply PCA is a dimensionality reduction technique that transforms the columns of a dataset into a set features called Principal Components. The objective is to represent the information in each column with the minimum columns possible.

![Principal Component Analysis](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2F4.bp.blogspot.com%2F-8yL0y5A5P2c%2FXHC_XVv4yaI%2FAAAAAAAAAPw%2Fr0IMUzkCFmocpVWVXdAv-X8OSZEm1w4FwCLcBGAs%2Fs1600%2Ffig_pca_illu3d.png&f=1&nofb=1)

## Long short-term memory neural networks
In this project, the main goal was to take advantage of recurrent neural networks to recognize patterns in stock market time series. What differentiates Recurrent Neural Networks and Long Short-Term Memory is that they consider time and sequence into account, they have a temporal dimension.

### What are LSTM networks?
We, humans, don't start thinking from scratch - every thought is based on previous knowledge, thoughts have persistence. Traditional neural networks don't do this, this is way recurrent neural networks are good! They address this problem by looping inside them, allowing the information to persist. However LSTM networks are a special kind of RNN, capable of learning long-term dependecies, they are explicitly designed to avoid the problem, remembering information for long periods of time is practically their default behavior. Inside them, it is better explained with a gif.
![LSTM Networks inside](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn-images-1.medium.com%2Fmax%2F1600%2F1*VOXRGhOShoWWks6ouoDN3Q.gif&f=1&nofb=1)

### Ridge Linear Regression Model
Ridge regression is a model tuning method that is used to analyse any data that suffers from multicollinearity. This method performs L2 regularization, when we have multicollinearity issues, least-squares are unbiased, and variances are large, this result in poor predictions. For ridge regression, a lambda term is aggregated in the cost function, lambda is denoted by alpha. So, controlling alpha, we alter the penalty term. Higher values of alpha, indicates a bigger penalty and therefore the magnitude of coefficients is reduced. It shrinks the parameters to prevent multicollinearity, in doing this, it reduces the model complexity.  
*The first step in building a Ridge Linear Regression model, is to standardize the variables!*
![](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fraw.githubusercontent.com%2Fwu-wenxiang%2FMedia-WebLink%2Fmaster%2Fqiniu%2Fcc248ddcba014c3cb4a2bb4cf75eb863-polynomial-ridge-regression.gif&f=1&nofb=1)
