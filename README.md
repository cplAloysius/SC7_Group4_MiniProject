# Fake News Detection
## About
This is our mini-project for SC1015 Introduction to Data Science and Aritificial Intelligence. Our project is on fake news detection where we attempt to identify features of fake news that differ from factual news. [Click here](https://github.com/cplAloysius/SC7_Group4_MiniProject/blob/main/DataPrep%2BEDA%2BML.ipynb) to view our project source code.
## Problem Definition
Can fake news be detected based on specific features that identify them as fake?
## The Dataset
[Gettting Real about Fake News](https://www.kaggle.com/datasets/mrisdal/fake-news)
## Data Cleaning and Preparation
- For Exploratory Data Analysis
  - Filled NULL entries in “country” column with value “US”
  - Removed countries with less than 20 entries
  - Removed all non-English entries
  - Removed irrelevant columns
  - Removed remaining rows with missing values
  - Removed entries where spam_score = 0 as it was skewing the distribution
  - Converted spam_score from numerical to categorical
  - Tokenise "title" column to analyse words used in title
  - Removed punctuations, non ascii characters, stop-words (common English words that are irrelevant for analysis)
  - Added new column "count_punct" which is the number of punctuations used in the title of each news thread
- For Machine Learning
  - Tokenise "title" and "text" column
  - Removed punctuations, non ascii characters, stop-words (common English words that are irrelevant for Machine Learning)
  - Split into n-grams of 1 to 3 words
## Exploratory Data Analysis
- Participants_count has the strongest negative correlation with spam_score, suggests a linear relationship between participants/engagement and news not being fake
- "informationclearinghouse.info" is a potential fake news site
- Buzz words or "click-baity" words such as "World-War 3" or "Yuge" used to lure people into clicking on fake news
- Possible relationship between use of punctuations in title and spam_score
- "ijr.com" is another potential fake news site
- Engagement and participation for news with high spam_score are lower than those with low and medium spam_score, with the exception of number of comments which remained consistent throughout
## Machine Learning
- Variables:
  - TF-IDF Matrix: Term Frequency and Inverse Document Frequency Matrix to measure importance of words in "title" and "text"
  - Categorical variables (author, site URL, country)
- Train-test split: 70:30 ratio
- Model used: [K-Nearest Neighbours](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm)
  - Chosen as it does not make assumptions about the distribution of spam_scores
  - It makes predictions based on similarity of test data points to train data points
- K-Value of 12 was chosen as it has the least error rate
- Precision: The ratio of no. of correctly predicted in a class / total no. of correctly predicted
- Test set had good precision across all spam_scores
  - high: 0.80
  - medium: 1.00
  - low: 0.77
- Recall: ratio of correct positive predictions for a class / total no. of observations in that class
- Recall for high and medium spam_score lower (0.13 and 0.08) compared to low spam_score (0.99)
  - medium and high spam_scores predicted as low instead
## Conclusion
- Assumptions were made for how certain factors corelated with news being fake
- Exploratory data analysis was used to confirm these assumptions
- Features that contribute to a news being fake were identified
  - Text used in titles
  - Author
  - Engagement/participants
- KNN classifier predicted based on these variables and supports claims
