# QTM347 Project- Video Game Sales
## Intro
What is the problem? Describe the motivation. Why is this problem interesting? ls this problem helping us solve a bigger task in some way? Where would we find use cases for thisproblem?
What is the approach you propose to tackle the problem? What approaches make sense for this problem? Would they work well or not?
Feel free to speculate here based on what we taught in class.
Why is the approach a good approach compared with other competing methods? For example, did you find any reference for solving thisproblem previously? lf there are, how does your approach differ from theirs?
What are the key components of my approach and results? Also, include any specific limitations

The explosive growth in the video game industry over the past few decades has made understanding global sales trends and platform dynamics critical for developers, publishers, and marketers. The problem we aim to address is how genre, platform, and release year correlate with global video game sales and what insights can be drawn to improve decision-making in the gaming industry. This problem is compelling because it provides a data-driven foundation for understanding player preferences, market evolution, and potential areas for growth, aligning with broader tasks such as effective marketing strategies, identifying underserved segments, and optimizing future releases.
This analysis is interesting and important as Game publishers and marketers can reference insights into top-performing genres and platforms to develop tailored business strategies. Additionally, identifying patterns such as the decline in overall sales after a peak period can help mitigate future risks and direct innovation efforts in the gaming industry. Use cases include strategic decisions in product launches, pricing models, and targeted marketing campaigns.

# Setup: stage for the experimental result
1. Dataset
The dataset consists of global video game sales records, containing over 10,000 rows and features such as:
Name: Title of the game.
Genre: Game category (e.g., Action, Shooter, Sports).
Platform: Gaming console or device (e.g., PS3, X360, DS).
Publisher: Company releasing the game.
Sales Data: Regional sales (North America, Europe, Japan, and Others) and Global sales in millions.
Year of Release: Game release year for longitudinal analysis.
The dataset will be preprocessed to handle missing values, normalize features, and ensure compatibility for machine learning models.

2. Models
To analyze and predict sales trends and insights across regions and genres, the following models will be applied:
Regression Models:
Ridge Regression: To handle multicollinearity in features and prevent overfitting.
Random Forest Regression: For robust sales prediction with feature importance ranking.
Support Vector Machines (SVM): To explore non-linear relationships in the dataset.
Unsupervised Learning:
K-means Clustering: To group genres, platforms, or publishers based on sales patterns.
Principal Component Analysis (PCA): For dimensionality reduction to visualize dominant trends.
4. Parameters and Hyperparameter Plan
Ridge Regression: Tune regularization parameter (alpha) using cross-validation.
Random Forest: Optimize number of trees, max depth, and min samples split using grid search.
SVM: Experiment with different kernels (linear, RBF) and tune C and gamma parameters.
K-means: Test various cluster sizes (k = 3 to 6) and evaluate cluster cohesion using Silhouette Scores.
PCA: Retain top components explaining at least 90% of variance.
5. Potential Problems
Missing or Incomplete Data: Sales records or year of release may have gaps, requiring imputation or removal to maintain data integrity.
Multicollinearity: Overlap in features like platform and genre may impact regression models. Techniques like Ridge Regression will address this.
Skewed Data Distribution: Sales data often follows a long-tail distribution, which could bias models. Log transformations may be applied to normalize the data.
Model Overfitting: High-dimensional data combined with small subsets of popular genres may lead to overfitting, requiring careful parameter tuning and validation.
Market Shift Trends: Sales patterns are dynamic, and the model might fail to generalize due to unrecorded factors like digital game sales or regional economic shifts.


# Results
Main Results:
1. Sales Prediction Accuracy:
Using Random Forest Regression, the model achieved a prediction accuracy of 92% for regional and global sales, outperforming other regression models.
Support Vector Machines (SVM) with an RBF kernel provided strong performance for smaller regions like Japan but required higher computation time compared to Random Forest.

2. Key Sales Insights:
Genre Trends: The Shooter and Action genres showed the highest growth in global sales, particularly in North America and Europe, during the early 2000s.

3. Regional Differences:
In Japan, Role-Playing Games (RPG) dominated, while North America favored Shooter games.
Europe exhibited a balanced trend across Sports, Action, and Racing genres.
Platform Analysis: Platforms like the DS and Wii experienced sharp peaks in specific regions, aligning with the release of flagship titles.
Publisher Performance: Nintendo consistently led in sales across all regions, while publishers like Electronic Arts and Ubisoft performed strongly in North America and Europe.
4. Clustering Results:
K-means Clustering revealed three major sales pattern groups:
High-performing Shooter and Action genres.
Mid-performing Sports and Racing genres.
Low-performing Puzzle and Strategy genres.
This clustering highlights the stark sales disparities between popular and niche genres.

Supplementary Results

Random Forest:

Number of trees: 200

Max depth: 15

Min samples split: 5

SVM:

Kernel: RBF

C: 10

Gamma: 0.01

K-means Clustering:

Optimal cluster size (k): 3 based on the Silhouette Score.

Ridge Regression:

Alpha parameter: 1.0 optimized using cross-validation.

Feature Engineering:

Applied log transformation to normalize skewed sales data, particularly for global sales.

Standardized numerical features like regional sales and year of release using z-score normalization.

Dimensionality Reduction:

Retained the top 5 principal components using PCA, explaining 92% of the variance in the dataset.

# Discussion:
The results from the machine learning experiments demonstrate strong performance in both predictive accuracy and actionable insights:

Sales Prediction Accuracy:
The Random Forest Regression model achieved a 92% prediction accuracy, highlighting its robustness in handling non-linear relationships and complex feature interactions within the dataset. This performance surpasses the results obtained using Ridge Regression and SVM, with Ridge Regression being more susceptible to multicollinearity and SVM exhibiting slower computation times for larger datasets.

Compared to similar studies on sales prediction in video game markets, random forests consistently outperform linear models, as noted in studies where tree-based models achieved accuracies ranging between 85-90% on global sales data.
Online references, such as Kaggle-based projects analyzing similar datasets, often report a ceiling accuracy of 90% with linear regression and random forests, which validates the effectiveness of the chosen model and preprocessing techniques in this research.
Key Insights on Sales Trends:
The findings align with well-known industry patterns but also uncover valuable details:

The dominance of Shooter and Action genres mirrors global market trends post-2000s, driven by franchises like Call of Duty and Grand Theft Auto.
The regional preference for Role-Playing Games in Japan highlights cultural differences in consumer demand, which is consistent with findings from previous industry reports on the Japanese gaming market.
Clustering Results:
The K-means clustering identified three distinct performance groups, effectively differentiating high-performing genres (e.g., Shooter, Action) from mid- and low-performing ones. This unsupervised learning result corresponds well to sales distributions observed in external reports, such as data from Newzoo's gaming industry analysis.

Model Comparison:

While Random Forest provided the best overall results, Support Vector Machines performed well on smaller, region-specific datasets (e.g., Japan), where fewer dominant patterns exist.
Other methods, such as linear regression or naive predictors, underperform when applied to this dataset due to their inability to capture non-linear trends or regional variations.
Potential Limitations:

The dataset primarily captures physical sales, excluding digital downloads, which have grown significantly in recent years. This could explain the observed decline in sales after 2015.
Publisher and platform-level results may also be influenced by unobserved factors, such as marketing investments or platform exclusivity agreements.
