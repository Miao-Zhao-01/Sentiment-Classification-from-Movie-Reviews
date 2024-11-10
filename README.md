# Sentiment Classification from Movie Reviews
The work presented in this report focuses on the sentiment classification task. Using movie reviews on Rotten Tomatoes as data, we implement six data representation methods to transform the natural language sentences into vectors and classify them into different sentiment categories (positive and negative) with four machine learning models. The best outcome is achieved by Logistic Regression model with the TF-IDF transformation (AUC-ROC value of 0.772). We also apply the same methods to the multiclass classification tasks and discuss how the imbalanced data distribution affects the results.

# Data Set
We conduct our experiments on the Stanford Sentiment Treebank data set [9], which consists of a total of 215,154 unique phrases from movie reviews on Rotten Tomatoes. Each phrase is labeled with a positivity probability that shows the degree of sentiment that the phrase expresses. In that case, all the sentences can be divided into five classes by mapping the corresponding probability using the cut-offs ([0, 0.2], (0.2, 0.4], (0.4, 0.6], (0.6, 0.8], (0.8, 1.0]) for very negative, negative, neutral,positive, very positive, respectively. We only use the instances that are complete sentences as our selected data set in order to simply the task. The selected data set includes 11,285 sentences and is split into training, validation, and test set. There are 8,116; 1,044; 2,125 instances in the training, validation, and test set, respectively.

<img width="798" alt="image" src="https://github.com/user-attachments/assets/ff59fb1d-24c4-42d0-b448-c28b59679dc3">


