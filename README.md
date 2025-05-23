# 📊 Twitter Sentiment Analysis Using Sentiment140

This repository contains a complete pipeline for performing sentiment analysis on tweets using the [Sentiment140 dataset](https://www.kaggle.com/datasets/kazanova/sentiment140). It includes data preprocessing, sentiment scoring using VADER, exploratory analysis, and insights visualized over time and frequent word usage.

---

## 📁 Dataset Overview

- **Source**: [Kaggle - Sentiment140 Dataset](https://www.kaggle.com/datasets/kazanova/sentiment140)
- **Total Records**: 1,600,000 tweets
- **Fields**:
  - `target`: Sentiment polarity (0 = negative, 4 = positive)
  - `ids`: Tweet ID
  - `date`: Timestamp of the tweet
  - `flag`: Query (unused, e.g., NO_QUERY)
  - `user`: Username
  - `text`: Tweet content

---

## 🎯 Project Objective

Analyze and visualize sentiment trends from tweets using natural language processing (NLP) techniques and derive meaningful insights from public sentiment on Twitter.

---

## 🔧 Pipeline Overview

### ✅ 1. Data Preprocessing

- Renamed columns and added headers
- Converted the `date` column to timezone-aware datetime
- Localized to `UTC` and converted to `US/Pacific`
- Extracted additional features: `month`, `cleaned_text`

### ✅ 2. Text Cleaning

- Removed:
  - Usernames (e.g., `@user`)
  - URLs (e.g., `http://...`)
- Trimmed whitespace and special characters

### ✅ 3. Word Frequency Analysis

- Tokenized cleaned tweets
- Removed English stopwords
- Applied lemmatization
- **Top 5 Most Frequent Words**:
  | Word | Frequency |
  |------|-----------|
  | day  | 103,289   |
  | good | 90,906    |
  | get  | 86,148    |
  | like | 79,605    |
  | go   | 78,132    |

### ✅ 4. Sentiment Analysis (VADER)

- Used `SentimentIntensityAnalyzer` from NLTK
- Calculated compound sentiment score
- Classified tweets as:
  - `positive` (score > 0)
  - `neutral` (score = 0)
  - `negative` (score < 0)

---

## 📈 Sentiment Trends by Month

| Month | Negative (%) | Neutral (%) | Positive (%) |
|-------|--------------|-------------|---------------|
| April | 23.22%       | 27.28%      | 49.50%        |
| May   | 22.48%       | 26.96%      | 50.57%        |
| June  | 29.31%       | 26.77%      | 43.92%        |

> 📌 **Insight**: Positive sentiment consistently dominates, with a spike in negativity in June.

---

## 📊 Visualizations

- 📅 **Monthly sentiment distribution**
- 📈 **Word frequency distribution**
- 🧠 **Sentiment trends based on VADER scoring**
- 📊 **Stacked bar plots of sentiment classes per month**

---

## 🔍 Key Insights

- **Most used word**: `day`, indicating daily life commentary dominates.
- **Positive sentiment** was highest in **May**, while **June** had a higher rate of negativity.
- Words like `good`, `get`, and `go` vary based on context and drive mixed sentiments.
- VADER provides reliable sentiment detection, aligning with labeled data.

---

## 📚 Libraries Used

- `pandas`
- `matplotlib`
- `seaborn`
- `nltk` (for VADER, tokenization, lemmatization)
- `re` (for regex-based text cleaning)

---

## 🚀 Getting Started

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/sentiment140-analysis.git
   cd sentiment140-analysis
