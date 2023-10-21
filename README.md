# CryptoClustering_unsupervise_learningmachine
Data Preprocessing:
I began by importing essential libraries such as pandas, hvplot, and various modules from scikit-learn. After loading the cryptocurrency market data into a DataFrame, I examined its structure and generated summary statistics.
Exploratory Data Analysis:
I visualized the data to get a feel for the distribution and relationships between variables using hvplot. This step is crucial because it gives me an initial sense of how the data might cluster.
Data Scaling:
Recognizing that features might be on different scales, I normalized the data using the StandardScaler() from scikit-learn to ensure that all features contribute equally to the distance computations in K-means.
Elbow Curve for Optimal K:
I ran a loop over potential cluster numbers (k-values) and calculated the inertia for each. By plotting the inertia values (Elbow Curve), I identified the optimal k-value, which appeared to be 4, as the point where the reduction in inertia begins to slow.
K-means Clustering on Original Data:
Using the optimal k-value, I fitted a K-means model on the scaled data, assigned cluster labels to each cryptocurrency, and visualized the clusters on a scatter plot with 24-hour and 7-day price changes as the axes.
Dimensionality Reduction using PCA:
I implemented Principal Component Analysis (PCA) to reduce the feature dimensions. After transforming the data into three principal components, I analyzed the explained variance to determine the amount of information retained. I found out that the three components explained about 89.5% of the total variance.
Elbow Curve and K-means on PCA Data:
Repeating the elbow method on PCA-transformed data, I again found that the optimal k-value was 4. I then applied K-means clustering on this PCA data and visualized the results.
Comparison of Results:
I created a composite visualization that displayed both the elbow curves and cluster plots side by side for the original and PCA-transformed data.
In conclusion, throughout this challenge, I have employed unsupervised learning techniques to analyze how cryptocurrencies might be grouped based on their 24-hour and 7-day price changes. By reducing dimensionality with PCA, I aimed to capture the most variance with fewer features, making the clustering process more efficient. However, this dimension reduction might lead to a loss of some information. After analyzing the clusters, it appears that using fewer features through PCA provides a clearer distinction between groups, suggesting that dimension reduction might be beneficial in this case.
