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
  - Removed entries where spam_score = 0
  - Converted spam_score from numerical to categorical
  - Tokenise "title" column to analyse words used in title
  - Removed punctuations, non ascii characters, stop-words (common English words that are irrelevant for analysis)
  - Added new column "count_punct" which is the number of punctuations used in the title of each news thread
- For Machine Learning
  - Tokenise "title" and "text" column
  - Removed punctuations, non ascii characters, stop-words (common English words that are irrelevant for Machine Learning)
## Model Used
K Nearest Neighbors Algorithm
## Conclusion
- Assumptions were made for how certain factors corelated with news being fake
- Exploratory data analysis was used to confirm these assumptions
- Features that contribute to a news being fake were identified
- KNN classifier supports these claims
