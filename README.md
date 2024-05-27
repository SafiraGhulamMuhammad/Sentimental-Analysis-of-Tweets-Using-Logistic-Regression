# Sentiment Analysis of Tweets Using Logistic Regression

This project performs sentiment analysis on a dataset of 10,000 tweets using Logistic Regression, a supervised machine learning algorithm. The dataset is evenly split between positive (5,000) and negative (5,000) tweets. The goal is to classify tweets as positive (1) or negative (0) based on their content.

## Steps Involved

### 1. Data Preprocessing
- **Remove Retweets, Hashtags, and URLs**: These elements do not contribute to sentiment.
- **Convert to Lowercase**: Ensures consistency in word comparison.
- **Tokenization**: Splits text into individual words.
- **Remove Stopwords and Punctuation**: Eliminates words like 'and', 'the'.
- **Stemming**: Reduces words to their root form (e.g., 'running' to 'run').

### 2. Feature Extraction
- **Sparse Representation**: Binary vectorization based on vocabulary; inefficient due to large space requirements.
- **Frequency Table Representation**: Reduces feature size to 3 dimensions:
  - `X = [1, sum(positive frequencies), sum(negative frequencies)]`.

### 3. Logistic Regression Model
- **Model Training**: Train on the dataset to classify tweets.
- **Cost Function**: Calculate error by comparing predicted and original labels.
- **Parameter Optimization**: Use gradient descent to minimize cost.

### 4. Prediction and Testing
- **Predict Function**: Classify new tweets as positive or negative.
- **Test Logistic Function**: Evaluate model performance by checking if predicted probabilities are greater than 0.5 (indicating a positive tweet).
### Here preprocessing and frequency count function is present in utils_LR.py
