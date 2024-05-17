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

