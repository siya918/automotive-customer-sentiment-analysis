# automotive-customer-sentiment-analysis
Automotive Customer Sentiment Analysis and Review Clustering 

# Automotive Customer Sentiment Analysis and Review Clustering

## Project Overview
In this project I analysed customer reviews for three car models from 
2009 — the Honda Accord, Hyundai Sonata, and Toyota Corolla — alongside 
2008 Honda Accord reviews, with the goal of determining which car achieved 
the highest customer satisfaction rate and whether Honda Accord satisfaction 
improved year over year. I also clustered the 2008 Honda Accord reviews 
into meaningful groups using unsupervised learning.

---

## What I Did

### Data Loading and Comment Counting
I began by loading four datasets of customer car reviews and counting 
the number of comments in each. I found that the 2008 Honda Accord had 
the most reviews at 540, followed by the 2009 Hyundai Sonata at 262, 
the 2009 Toyota Corolla at 226, and the 2009 Honda Accord at 224 — 
giving a total of 1252 comments across all four datasets.

### Text Cleaning and Preprocessing
I built a text cleaning pipeline that removed HTML tags such as DOC, 
TEXT, and AUTHOR, stripped numerical characters, converted all text to 
lowercase, removed stopwords, and applied lemmatization. I chose 
lemmatization over stemming deliberately — stemming produces 
non-existent root forms such as reducing comparing to compar, which 
destroys the semantic meaning of the word. Lemmatization preserves 
real dictionary words and their part of speech, producing cleaner and 
more interpretable text for downstream analysis.

### Sentiment Analysis
I used TextBlob to perform sentiment analysis on all four review 
datasets, classifying each comment as positive, neutral, or negative 
based on its polarity score. I then calculated average sentiment scores 
per dataset to compare overall customer satisfaction across car models 
and years.

**2009 model comparison:**
- 2009 Hyundai Sonata achieved the highest average sentiment at 0.091
- 2009 Toyota Corolla followed at 0.082
- 2009 Honda Accord scored 0.072

**Year over year Honda Accord comparison:**
- 2008 Honda Accord average sentiment: 0.035
- 2009 Honda Accord average sentiment: 0.072
- Customer satisfaction improved by 0.04 from 2008 to 2009

### Word Cloud Visualisation
I generated word clouds for each of the four review datasets to 
visualise the most frequently occurring words. I customised the word 
clouds by removing car brand names — Honda, Accord, Toyota, Corolla, 
Hyundai, Sonata — to surface more meaningful thematic words beyond 
the obvious brand mentions.

### Visualisation and Evaluation Metrics
I produced several additional visualisations to support the analysis 
including a grouped bar chart comparing positive, neutral, and negative 
comment counts across all four datasets, pie charts showing sentiment 
distribution percentages per car model, a bar chart comparing average 
sentiment scores across the three 2009 models, a line chart showing 
Honda Accord sentiment improvement from 2008 to 2009, and sentiment 
score distribution histograms for both Honda Accord datasets.

### K-Means Clustering — Optimal K Selection
I applied K-Means clustering to the 2008 Honda Accord reviews to 
group them into meaningful categories. I first converted the cleaned 
reviews into a Term Frequency Inverse Document Frequency (TF-IDF) 
feature matrix, then used the Elbow Method — plotting Within Cluster 
Sum of Squares (WCSS) for k values of 2 through 5 — to determine the 
optimal number of clusters. The elbow appeared at k=3, indicating 
three natural groupings in the 2008 review data.

### Extended Clustering with Combined Data
As an optional extension I combined the 2008 and 2009 Honda Accord 
reviews and reran the clustering analysis. The optimal k increased 
to 4, demonstrating that as the dataset grew in size and complexity 
more clusters were required to represent the underlying patterns — 
a finding that aligns with the expected behaviour of K-Means on 
larger, more diverse text corpora.

---

## Key Findings
- The 2009 Hyundai Sonata achieved the highest customer satisfaction 
  among the three 2009 models based on average sentiment score
- Honda Accord customer satisfaction improved meaningfully from 2008 
  to 2009, with average sentiment nearly doubling from 0.035 to 0.072
- The 2008 Honda Accord reviews naturally cluster into three groups, 
  expanding to four when combined with 2009 reviews
- Lemmatization consistently produced more interpretable and 
  linguistically valid tokens than stemming across all review datasets

---

## Technology Stack
- Python
- Natural Language Toolkit (NLTK) — tokenisation, lemmatisation, 
  stopword removal
- TextBlob — sentiment polarity analysis
- scikit-learn — Term Frequency Inverse Document Frequency 
  vectorisation, K-Means clustering
- WordCloud — word cloud generation
- matplotlib — all visualisations
- pandas — data manipulation
- re — regular expression based text cleaning

---

## Dataset
Four datasets of customer car reviews:
- 2008 Honda Accord — 540 reviews
- 2009 Honda Accord — 224 reviews
- 2009 Hyundai Sonata — 262 reviews
- 2009 Toyota Corolla — 226 reviews

---

## Academic Context
This project was completed as the final assessment for STK 353 at the 
University of Pretoria. It demonstrates applied Natural Language 
Processing techniques including text preprocessing, sentiment analysis, 
unsupervised clustering, and data visualisation on real customer review 
data.
