# NLP---News_Article_Analyzer
 It is a repository for advanced Natural Language Processing techniques, specializing in article analysis for category classification, sentiment classification, and summarization.
# NewsNuggets

"NewsNuggets" is a comprehensive solution designed to simplify news consumption in today's information-rich environment. Leveraging advanced natural language processing (NLP) and machine learning techniques, the platform swiftly summarizes news articles, categorizes them by topics, and analyzes their sentiments. This streamlined approach empowers users to stay informed about crucial updates without the overwhelming volume of data, enabling efficient access to essential insights while saving time and effort.

# Methodology
## Data Collection: 
The BBC Dataset consists of 2,225 documents collected from the BBC News website, corresponding to stories published in five topical areas during 2004-2005. It is categorized into five class labels: business, entertainment, politics, sport, and tech. The sentiment dataset consists of sentiment categories: positive and negative. The data collection aims to provide a comprehensive resource for developing and testing document classification, and other text analysis methods.
## Data Preprocessing: 
This initial stage involves examining thedata to understand its characteristics and underlying patterns. Text preprocessing is a critical component of the process, which includes several key steps: tokenization to break down text into smaller parts, removal of URLs and punctuation to clean the text, conversion of all text to lowercase to maintain consistency, and removal of stopwords to eliminate unnecessary words. Additionally, lemmatization is performed to reduce words to their base or root form, further refining the textual data. For text vectorization, techniques such as Bag of Words (BoW) and Term Frequency-Inverse Document Frequency (TF-IDF) are employed to convert text into a numerical format that can be processed by machine learning models. The data is split into training and testing sets (80-20 split). There is an imbalance in the news sentiment dataset, with most of the documents having a positive sentiment. To address this, the Synthetic Minority Over-sampling Technique (SMOTE) is applied to the training set to balance the dataset effectively.

<img width="1127" alt="image" src="https://github.com/Anitha-Balachandran/NLP---News_Article_Analyzer/assets/143915040/df2b888b-28a7-48aa-828b-fb4ba869a499">

# Model Details and Training
The details and training process for three different functionalities of the NewsNuggets application are outlined below.

## News Category Classification 
Based on a literature review of news category classification as a multi-class classification problem, five different models were identified and implemented: Logistic Regression, Decision Tree Classifier, Multinomial Naive Bayes, Random Forest Classifier, and AdaBoost Classifier. These models were utilized with a combination of BoW and TF-IDF vectors, resulting in a total of 10 different model configurations. While most research on news article classification focused on Grid Search, Bayesian optimization was less frequently experimented with. Bayesian optimization was chosen for its efficiency in exploring hyperparameter spaces by considering past performance. The models were trained and validated for multiple hyperparameters.

## News Sentiment Classification 
News sentiment binary classification is similar to category classification. However, during exploratory data analysis, the positive sentiment class was found to be significantly higher than the negative sentiment class, causing an imbalance in the dataset. To address this, the SMOTE is applied, increasing samples in the minority class to create a balanced dataset. After applying SMOTE, both positive and negative classes have an equal number of samples. The classification process then proceeds similarly to news category classification. Five models are selected: Logistic Regression, Decision Tree Classifier, Random Forest Classifier, AdaBoost Classifier, and Multinomial Naive Bayes Classifier. Two vectorization methods, TF-IDF and Bag of Words, are used, creating a combination of 10 distinct models. Bayesian optimization is then utilized for hyperparameter tuning to validate different hyperparameters.

## News Summarization
This section presents the implementation of three distinct extractive summarization techniques on the BBC News Dataset derived from the literature survey. While most summarization surveys utilized complex abstractive models, this goal was achieved using a straightforward extractive summarization approach with similar summarization quality. The Word Frequency-based Summarization, TF-IDF-based Summarization, and TextRank Summarization techniques represent a unique approach to the challenge of text summarization, which is critical in managing the vast amount of information generated daily.
- Word Frequency Summarization: This method relies on the frequency of occurrence of words within the text. Words that appear more frequently are considered more important, and sentences containing these words are selected to create the summary.
- TF-IDF Summarization: This technique evaluates both the frequency of words and the importance of words across documents using the Term Frequency-Inverse Document Frequency (TF-IDF) metric. It helps in identifying significant words in each document for summary generation.
- TextRank Summarization: Utilizing a graph-based ranking model, this method is inspired by algorithms like PageRank. It involves building a graph where sentences are nodes, and edges are based on the similarity between sentences. The ranking of each sentence determines its likelihood of inclusion in the summary.

# Experiments and Evaluation Results
The experiments and evaluation results for the three functionality models explained above are detailed below.
## News Category Classification 
News Category Classification is fundamental for enhancing information retrieval and organizational efficiency. To assess the effectiveness of the trained models, evaluation metrics such as the confusion matrix, accuracy, precision, recall, and F1-score were utilized.
Hyperparameter Tuning Results: The models were fine-tuned using Bayesian optimization with cross-validation, employing 5 folds and 32 iterations, and leveraging parallel processing to expedite the process and enhance performance. Based on the mean validation accuracy and ranking, the best parameter combinations for the 10 models were chosen. These fine-tuned models were then evaluated on the test set, and the model with the best performance was identified, as shown in Table 1. The Logistic Regression model with TF-IDF vectorization achieved a test accuracy of 98% compared to BoW. The classification report for this model showed an overall accuracy of 0.986, with a weighted average precision, recall, and F1-score of 0.99. The best parameters for the Logistic Regression model were: C=8.4117, max_iter=198, penalty='l2', and solver='lbfgs'. Figure 2 shows the learning curve, demonstrating high accuracy and good generalization as the number of training examples increases, stabilizing around a validation mean score of 0.9764. Figure 3 shows the confusion matrix, demonstrating high accuracy with most categories (entertainment, business, sport, politics, tech) having minimal misclassifications, indicating strong performance across all classes.
     
<img width="828" alt="image" src="https://github.com/Anitha-Balachandran/NLP---News_Article_Analyzer/assets/143915040/b3603dbe-ce24-4141-bce4-dee53c169ecb">

## News Sentiment Classification 
In binary sentiment classification, the evaluation of models is performed using various metrics such as accuracy, precision, recall, F1-score, confusion matrix, and ROC curve. All ten models were fine-tuned using Bayesian optimization with cross-validation. Table 2 shows the evaluation results of these models. Logistic Regression with TF-IDF emerged as the top-performing model, achieving an impressive accuracy of 96.6%. The best combination of hyperparameters for the Logistic Regression model was: penalty='l2', C=9.24, max_iter=138, and solver='liblinear'. Figure 4 shows the confusion matrix with only 11 misclassifications, demonstrating the model's robustness. The ROC curve demonstrated good discriminative ability, with an AUC score of 0.99, as shown in Figure 5.

<img width="826" alt="image" src="https://github.com/Anitha-Balachandran/NLP---News_Article_Analyzer/assets/143915040/413442c4-c6fc-4751-b761-913689d39272">

## News Summarization
The summarization models were evaluated using the ROUGE and BLEU metrics, which evaluate the quality of text summaries by comparing them to reference summaries. The Table 3 below presents the scores for each model across different metrics:

<img width="827" alt="image" src="https://github.com/Anitha-Balachandran/NLP---News_Article_Analyzer/assets/143915040/4744e3d0-ec43-4320-8d30-77c0c768cf2a">

The TF-IDF model consistently outperformed the other two models across almost all metrics, indicating a superior ability to generate summaries that align closely with the reference texts. The Word Frequency model scored the highest in ROUGE-1 Recall (0.91), suggesting it effectively captures critical content from the original texts.
TextRank excelled in ROUGE-1 Precision (0.68) and ROUGE-L Precision (0.67), showing its strength in generating precise and relevant content, albeit with slightly lower overall effectiveness compared to TF-IDF. These results suggest that the TF-IDF method is generally more effective for summarizing news articles from the BBC News Dataset.

# Deployment
As part of the deployment process, the best classification and summarization models have been integrated into the “NewsNuggets” application. This application enables users to input news articles, which are then preprocessed, vectorized, and analyzed to provide results that are categorized, sentiment-analyzed, and summarized. For the user interface, HTML5 and CSS were employed to create a responsive and intuitive design, and the backend functionality was managed through a Flask application server. This architecture ensures that users experience a seamless and efficient interaction with the NewsNuggets application.

<img width="820" alt="image" src="https://github.com/Anitha-Balachandran/NLP---News_Article_Analyzer/assets/143915040/de4c4c85-38b1-4141-aea3-a055778368d3">




