Dimensionality Reduction

In the world of Big Data, oodles of observations are collected along with numerous different variables. When examining the differences between observations, these differences can become misleading due to the large number of variables included in the comparison. For example, when comparing how similar certain days of the year are, one may start with temperature, day of the month, and rainfall. In these simple variables, there may be some clear differences and clear similarities. The problem of too many dimensions occurs when adding more variables, such as the exact position of the stars and planets in the sky, the average pressure, humidity, etc. The addition of more variables reduces the probability that days will have more similarities and increases the probability the days will appear more different. Some variables may be so extreme, such as the exact position of stars and planets in the sky, that every day will appear different, which could muddle any statistical comparison. This issue is solved by dimensionality reduction. The reduction in dimensionality is achieved in three ways: feature elimination, feature selection, or feature extraction. 

Feature elimination is at it sounds, removing certain variables from the dataset. This option has the problem of not utilizing any information from these data, so they are essentially lost. Feature selection retains the most informative variables within the dataset to make predictions. An example of this method is conducting a stepwise regression analysis, where a regression model is calculated step by step using the variable with the largest significance in predicting Y and moving on to the next one. The last method, feature extraction, is conducted either through principal component analysis (PCA) or t-Distributed Stochastic Neighbor Embedding (t-SNE). These methods will be the focus of this paper. 
	
PCA is a linear mathematical technique which maximizes the variance between data points in a two-dimensional space. The variance is obtained by computing the eigenvector of a matrix containing the covariances of all the variables, which is called the covariance matrix. These eigenvectors create principal components which are the new features of the data that explain the variance. The technique attempts to maximize the amount of explanation of variance in each principal component so the lowest number of them can be used to explain the highest amount of variance. The two new features used to create a plot are also new variables that can be included in calculations.

t-SNE, unlike PCA, is a non-linear technique that uses probability to reduce dimensions. The methodology for creating a t-SNE plot is quite complex. The first step is to compute the probability of similarity in the original dataset and then in the reduced dataset. This similarity probability is computed as a conditional probability that a point is in a cluster with another in accordance to a normal distribution where the first point is the mean. This probability is then minimized when plotting on a two-dimensional graph. Because the datapoints are heavily augmented when graphing to two dimensions, the output cannot be used for a robust statistical analysis. Instead, it is used to glean information about the structure of the data visually. 

Utilizing these two techniques, large datasets can be analyzed without data being dropped, retaining precious information and increasing the accuracy of your final result.


References

Pathak, M. (2018, September). Introduction to t-SNE. Retrieved October 28, 2020, from https://www.datacamp.com/community/tutorials/introduction-t-sne

Jaadi, Z. (2020, October). A Step by Step Explanation of Principal Component Analysis. Retrieved October 28, 2020, from https://builtin.com/data-science/step-step-explanation-principal-component-analysis




