# Sentimental-Analysis-of-Tweets-Using-Logistic-Regression
Overview
This project aims to perform sentiment analysis on a dataset of tweets using a supervised machine learning algorithm, specifically Logistic Regression. The dataset comprises 10,000 tweets, evenly split between positive (5,000) and negative (5,000) sentiments. The goal is to train a Logistic Regression model to classify tweets as positive (1) or negative (0) based on their content.

Steps Involved
1. Data Preprocessing
Before feeding the data into the model, it is essential to preprocess it to ensure that it is in a suitable format for analysis. The preprocessing steps include:
Removing Retweets, Hashtags, and URLs: These elements do not contribute to the sentiment and can be removed.
Converting to Lowercase: This helps in maintaining consistency as 'Happy' and 'happy' should be treated as the same word.
Tokenization: Splitting the text into individual words.
Removing Stopwords and Punctuation: Words like 'and', 'the', etc., do not contribute to the sentiment analysis.
Stemming: Reducing words to their root form (e.g., 'running' to 'run').

2. Feature Extraction
Since the text data cannot be directly used for training the model, we need to convert it into numerical format. There are two methods considered here:
Sparse Representation:
Vocabulary Creation: Create a list of unique words from the dataset.
Binary Vectorization: For each tweet, create a binary vector where each element corresponds to a word in the vocabulary. If the word is present in the tweet, set the element to 1; otherwise, set it to 0.
Drawback: This method results in a large and sparse matrix, making it inefficient in terms of space and computation.
Frequency Table Representation
Frequency Count: Count the frequency of each word in positive and negative tweets.
Feature Vector: Create a 1x3 vector for each tweet as follows:
X = [1, sum(positive frequencies), sum(negative frequencies)]
Advantage: This reduces the feature size to just 3 dimensions, making it more efficient.
3. Logistic Regression Model:
Logistic Regression is used to classify the tweets. The steps involved include:
Model Training: Train the model on the training dataset, which contains both positive and negative tweets. The model will learn to classify tweets based on the features extracted.
Cost Function: Compare the predicted output with the original labels and calculate the cost (error).
Parameter Optimization: Use gradient descent to adjust the model parameters to minimize the cost until convergence.
4. Prediction and Testing
After training the model, we use the following functions:
Predict Function: To classify new tweets as positive or negative.
Test Logistic Function: To evaluate the model's performance by checking if the predicted probabilities (y_pred) are greater than 0.5 (indicating a positive tweet).
