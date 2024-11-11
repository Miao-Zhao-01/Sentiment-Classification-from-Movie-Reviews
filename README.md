# Sentiment Classification from Movie Reviews
The work presented in this report focuses on the sentiment classification task. Using movie reviews on Rotten Tomatoes as data, we implement six data representation methods to transform the natural language sentences into vectors and classify them into different sentiment categories (positive and negative) with four machine learning models. The Logistic Regression model achieves the best outcome with the TF-IDF transformation (AUC-ROC value of 0.772). We also apply the same methods to the multiclass classification tasks and discuss how the imbalanced data distribution affects the results.

# Data Set
We conducted our experiments on the Stanford Sentiment Treebank data set, which consists of 215,154 unique phrases from movie reviews on Rotten Tomatoes. Each phrase is labelled with a positivity probability that shows the degree of sentiment that the phrase expresses. In that case, all the sentences can be divided into five classes by mapping the corresponding probability using the cut-offs ([0, 0.2], (0.2, 0.4], (0.4, 0.6], (0.6, 0.8], (0.8, 1.0]) for very negative, negative, neutral, positive, very positive, respectively. We only use the instances that are complete sentences as our selected data set to simplify the task. The selected data set includes 11,285 sentences and is split into training, validation, and test sets. There are 8,116; 1,044; and 2,125 instances in the training, validation, and test set.

# Data Exploration
Figure 1 shows the positivity probability distributions of all training data and data in each class. As shown in Figure 1 1(a), the probability density curve has two peaks at about 0.2 and 0.8. These two values are the partition boundaries of “negative and very negative” and “positive and very positive”. We can also notice a similar trend in Figure 1(b), where the peaks of the curves for very negative and negative data are close, which is the same as the curves for positive and very positive data. It implies a possibility that there might be little differences between two sentences from two adjacent sentiment classes if their positivity probabilities are close to a partition boundary (i.e. 0.2 or 0.8).
<div align=center>
<img width="798" alt="image" src="https://github.com/user-attachments/assets/ff59fb1d-24c4-42d0-b448-c28b59679dc3">
</div>



We also use the wordcloud figures to visualize the word frequency of the training data. A wordcloud is a cluster of words depicted in different sizes. The bigger the word is in a wordcloud, the more frequently it appears within a text. Considering that there should be many neutral nouns like movie(s) and film(s) in the data, we remove those words first before generating the wordcloud figures. Figure 2 shows the wordcloud of all sentences and sentences in each class. Despite some neutral words like “time”, “story”, “character”, “work”, “make” etc., there are still some words of high frequency that can embody the feature of the corresponding class. For example, we can see several positive and commendatory words like “best”, “funny”, “well” and “good” in the wordcloud of (very) positive data. On the contrary, several negative and critical words like “little”, “bad”, “n’t” and “dull” are more frequent in the (very) negative sentences.
<div align=center>
<img width="776" alt="image" src="https://github.com/user-attachments/assets/73271bff-fd3c-4d0f-afc0-b71c7e1661db">
</div>

# Results
Figure 3 shows the binary classification results produced by different combinations of six vectorization methods and four machine-learning classifiers. The best performance on test data was achieved by the Logistic Regression model with TF-IDF transformation with an AUC-ROC value of 0.772. From the perspective of classifiers, the Logistic Regression model outperforms the other four models and the K Nearest Neighbors model is the worst-performing one in general. It should be noted that, although the Decision Tree model performs quite well on the training data and even the AUC-ROC value reaches 1.0 when using the PCA method, its results on the test data are not satisfactory. It may just suggest that the model is overfitted.
<div align=center>
<img width="595" alt="image" src="https://github.com/user-attachments/assets/7160f2ef-1ba6-4372-9d88-a5e5366da6e0">
</div>

# Main References
[1] Tomas Mikolov, Kai Chen, Gregory S. Corrado, and Jeffrey Dean. Efficient estimation of word representations in vector space. In International Conference on Learning Representations, 2013.  
[2] Vivek Narayanan, Ishan Arora, and Arjun Bhatia. Fast and accurate sentiment classification using an enhanced naive bayes model. In International Conference on Intelligent Data Engineering and Automated Learning, pages 194–201. Springer, 2013.  
[3] Anthony J. Myles, Robert N. Feudale, Yang Liu, Nathaniel A. Woody, and Steven D. Brown. An introduction to decision tree modelling. Journal of Chemometrics, 18(6):275–285, 2004.  
[4] Khin Phyu Phyu Shein and Thi Thi Soe Nyunt. Sentiment classification based on ontology and SVM classifier. In 2010 Second International Conference on Communication Software and Networks, pages 169–172, 2010.


