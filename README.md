# Israel-and-Palestine-geotagged-and-reply-tweets-dataset 
Dataset of tweets on Israel and Palestine from October 7, 2023 to April 4, 2024. 
For each of these tweets, sentiment prediction is performed using our fine-tuned BERT six basic sentiment classification model ((i.e., anger, fear, love, joy, sadness, and surprise)).
"all-tweets" means no-geotagged tweets and geo-tagged tweets.
"geo-tagged tweets" means the tweets with country information.

# Below are the step-by-step instructions on how to reproduce our study.
## Step 1: Make Tweets Dataset
### 1.1 Collect geotagged tweets. The code can be found at https://github.com/wdj1995/TextCNN_BiLSTM_BERT_sentiment_classification/tree/main/collect_geotagged_tweets (‘collect_tweets.py’). To collect tweets on different topics, you need to change the keyword in ‘collect_tweets.py’ and prepare a new JSON file with keywords in various languages.
### 1.2 Text preprocessing. Text preprocessing involves removing duplicate text, punctuation marks, emojis, and URLs. The preprocessed results can be found at https://github.com/wdj1995/Israel-and-Palestine-tweets-dataset (‘all-tweets-151400-01.xlsx’ and ‘all-tweets-151400-02.xlsx’).
## Step 2: Sentiment Classification
### 2.1 Fine-tune the BERT. The code can be found at https://github.com/wdj1995/TextCNN_BiLSTM_BERT_sentiment_classification/tree/main/fine-tuned%20BERT (‘dataset.py’, ‘train.py’, ‘modeling.py’, ‘analyzer.py’, and ‘evaluate.py’). The predicted results can be found at https://github.com/wdj1995/Israel-and-Palestine-tweets-dataset (‘all-tweets-151400-01.xlsx’ and ‘all-tweets-151400-02.xlsx’).
## Step 3: Sentiment propagation analysis
### 3.1 Collecting reply tweets. The code can be found at https://github.com/wdj1995/TextCNN_BiLSTM_BERT_sentiment_classification/tree/main/collect_reply_tweets (‘get_reply_tweets.py’ is used to get reply tweets, ‘get_country_info.py’ is used to get the location of X.com user). The reply tweets can be found at https://github.com/wdj1995/Israel-and-Palestine-tweets-dataset (‘geotagged-tweets-99526.xlsx’).
### 3.2 Exploring the sentiment exchange patterns between users. This work is carried out using Gephi (an open-source software). The data of community detection can be found at https://github.com/wdj1995/Israel-and-Palestine-tweets-dataset (‘community detection results.xlsx’). The figure of the sentiment propagation network is plotted by R Studio, the code can be found at https://github.com/wdj1995/TextCNN_BiLSTM_BERT_sentiment_classification (‘plot_the_sentiment_propagation_network.R’).
### 3.3 Exploring the spatial propagation patterns of sentiments. Since each reply tweet includes country information, we manually counted the spatial propagation of reply tweets within and between countries. The statistical data of reply tweets within and between countries can be found at https://github.com/wdj1995/Israel-and-Palestine-tweets-dataset (‘sentiment spatial propagation results.xlsx’).
### 3.4 Exploring main factors driving sentiment propagation. The codes can refer to https://github.com/wdj1995/TextCNN_BiLSTM_BERT_sentiment_classification/tree/main/time_series_cluster_and_random_forest. The ‘kmeans_clustering.py’ and ‘kmedoids_clustering.py’ are used for time-series clustering. The ‘random_forest_index_MDA.py’ and ‘random_forest_index_MDI.py’ are used to calculate the important indicators. The data for this part can be found at https://github.com/wdj1995/Israel-and-Palestine-tweets-dataset (‘statistical data for time series cluster and classify.xlsx’).

