# Customer-Feedback-Sentiment-Analysis-TASK-4
# NAME:MEHA MARY SAMUVEL
# DOMAIN:DATA ANALYTICS
# DURATION:4 WEEKS
# INTERN ID:CITS712
# PROJECT 1: sales-trend-visualization
# INTERN PERIOD: 17TH MAY-14JUNE

# SOURCE CODE
import pandas as pd
import matplotlib.pyplot as plt
from textblob import TextBlob

# Load dataset
df = pd.read_csv("customer_feedback.csv")

# Display first rows
print(df.head())

# Dataset information
print(df.info())

# Check missing values
print(df.isnull().sum())

# --------------------------------
# Sentiment Analysis Function
# --------------------------------

def get_sentiment(text):
    analysis = TextBlob(text)

    if analysis.sentiment.polarity > 0:
        return 'Positive'
    else:
        return 'Negative'

# Apply sentiment analysis
df['Sentiment'] = df['Review'].apply(get_sentiment)

# Display dataset with sentiment
print(df)

# --------------------------------
# Sentiment Count Visualization
# --------------------------------

sentiment_count = df['Sentiment'].value_counts()

sentiment_count.plot(kind='bar')

plt.title("Customer Feedback Sentiment")
plt.xlabel("Sentiment")
plt.ylabel("Count")

plt.show()
