# NLP---News_Article_Analyzer
 It is a repository for advanced Natural Language Processing techniques, specializing in article analysis for category classification, sentiment classification, and summarization.
# NewsNuggets

"NewsNuggets" is a comprehensive solution designed to simplify news consumption in today's information-rich environment. Leveraging advanced natural language processing (NLP) and machine learning techniques, the platform swiftly summarizes news articles, categorizes them by topics, and analyzes their sentiments. This streamlined approach empowers users to stay informed about crucial updates without the overwhelming volume of data, enabling efficient access to essential insights while saving time and effort.

<img width="1127" alt="image" src="https://github.com/Anitha-Balachandran/NLP---News_Article_Analyzer/assets/143915040/df2b888b-28a7-48aa-828b-fb4ba869a499">

#Methodology
##Data Collection: The BBC Dataset consists of 2,225 documents collected from the BBC News
website, corresponding to stories published in five topical areas during 2004-2005. It is
categorized into five class labels: business, entertainment, politics, sport, and tech. The
sentiment dataset consists of sentiment categories: positive and negative. The data collection
aims to provide a comprehensive resource for developing and testing document clustering,
classification, and other text analysis methods.

##Data Preprocessing: Figure 1 illustrates the workflow: This initial stage involves examining the
data to understand its characteristics and underlying patterns. Text preprocessing is a critical
component of the process, which includes several key steps: tokenization to break down text
into smaller parts, removal of URLs and punctuation to clean the text, conversion of all text to
lowercase to maintain consistency, and removal of stopwords to eliminate unnecessary words.
Additionally, lemmatization is performed to reduce words to their base or root form, further
refining the textual data. For text vectorization, techniques such as Bag of Words (BoW) and
Term Frequency-Inverse Document Frequency (TF-IDF) are employed to convert text into a
numerical format that can be processed by machine learning models. The data is split into
training and testing sets (80-20 split). There is an imbalance in the news sentiment dataset, with
most of the documents having a positive sentiment. To address this, the Synthetic Minority
Over-sampling Technique (SMOTE) is applied to the training set to balance the dataset
effectively.
