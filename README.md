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

# OUPUT
<img width="1828" height="770" alt="Image" src="https://github.com/user-attachments/assets/ea4fb0cd-37c0-4a72-9727-4d561a4412a4" />
<img width="903" height="455" alt="Image" src="https://github.com/user-attachments/assets/aada13bb-6f47-4746-be5a-45aeec23bc39" />
<img width="800" height="294" alt="Image" src="https://github.com/user-attachments/assets/894a691a-baf6-43bf-93b5-86e70206f3e8" />
<img width="789" height="367" alt="Image" src="https://github.com/user-attachments/assets/fb88b6e3-49ce-43ab-b985-0c1e061a0116" />
<img width="886" height="644" alt="Image" src="https://github.com/user-attachments/assets/6ff9da92-d482-4f4e-b3fa-b341dee3c931" />
