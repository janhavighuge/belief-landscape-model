# NLP Pipeline for Misinformation Detection & Behavioral Risk Analysis on Reddit (r/climate)

**Graduate Research Project | The SOURCE, Syracuse University**  
*September 2022 – June 2023*

---

## Project Overview

This project developed an end-to-end Natural Language Processing (NLP) and Machine Learning (ML) pipeline to analyze over **1 million Reddit posts** from the r/climate subreddit. The goal was to detect misinformation patterns, classify user intent, analyze sentiment trends, and identify behavioral risk signals associated with belief dynamics and misinformation spread.

The pipeline includes data collection, preprocessing, feature engineering, topic modeling, sentiment analysis, behavioral risk detection, and deployment of a Flask web app on Google Cloud Platform for real-time monitoring.

---

## Objectives

- Understand and classify topical themes and user intent within climate discussions
- Detect misinformation and behavioral risk markers such as hostility, conspiratorial language, and distress
- Improve sentiment analysis accuracy on social media text
- Deploy an automated, scalable pipeline for near real-time data processing and visualization

---

## Pipeline Architecture

### 1. Data Collection
- Scraped 1M+ posts using the Pushshift API from r/climate and related subreddits
- Extracted post text, metadata (author, timestamp, flair), and engagement metrics

### 2. Preprocessing
- Cleaned text by removing URLs, emails, and punctuation
- Tokenized posts and converted emojis to text (using `emoji.demojize`) to retain emotional content
- Preserved capitalization to capture emotional emphasis as a feature
- Removed stopwords, while retaining domain-specific terms

### 3. Feature Engineering
- TF-IDF vectors and Word2Vec embeddings to capture lexical and semantic information
- Metadata features such as post length, capitalization ratio, and posting time
- Emotion and sentiment features using NRC Emotion Lexicon and VADER sentiment analyzer

### 4. Topic Modeling & Intent Segmentation
- Applied BERTopic for unsupervised topic discovery, identifying 30+ meaningful topics such as Climate Denialism, Activism, and Policy Debate
- Used weak supervision (keyword rules, subreddit flairs) to label macro user intents like Activism, Denial, and Supportive

### 5. Sentiment Analysis
- Enhanced VADER baseline with a custom LSTM + GloVe embedding model
- Improved sentiment classification accuracy by 15% on 100K+ Reddit posts
- Visualized sentiment trends alongside topical shifts over time

### 6. Behavioral Risk Signal Detection
- Defined behavioral risk categories: Hostility, Hopelessness, Conspiratorial, Crisis, Call to Action
- Used weak supervision (keywords, punctuation, caps usage) to label risk signals
- Trained logistic regression and random forest classifiers achieving ~78% F1 score
- Clustered risky behaviors using UMAP and KMeans to identify belief escalation hotspots

### 7. Deployment
- Built a Flask web app deployed on Google Cloud Platform
- Automated data ingestion and prediction pipelines processing 400K+ posts daily
- Enabled researchers to monitor real-time belief dynamics, risk signals, and misinformation trends

---

## Results & Impact

- Improved sentiment analysis accuracy by **15%** on social media data  
- Achieved **85% accuracy** in user intent segmentation  
- Detected early warning signals for misinformation and belief polarization  
- Provided scalable, real-time monitoring capability for research teams  

---

## Technologies & Tools

| Category           | Tools & Libraries                                  |
|--------------------|---------------------------------------------------|
| Programming        | Python, Flask, HTML/CSS                            |
| Data Collection    | Pushshift API                                     |
| NLP & ML           | Scikit-learn, BERTopic, TensorFlow, Gensim, NLTK, VADER, UMAP, HDBSCAN |
| Visualization      | Matplotlib, Seaborn, Plotly                        |
| Deployment         | Google Cloud Platform (App Engine, Cloud Storage) |

---

## How to Use

1. Clone the repository  
2. Install dependencies from `requirements.txt`  
3. Run data ingestion scripts to collect Reddit posts  
4. Execute preprocessing and feature engineering modules  
5. Train or load pretrained topic, sentiment, and risk detection models  
6. Launch the Flask app locally or deploy on GCP for real-time monitoring

---

## Future Work

- Incorporate transformer-based models (e.g., BERT) for improved context understanding  
- Expand behavioral risk detection with multimodal data (images, videos)  
- Develop dashboards for stakeholder-friendly visualization and alerts  

---

## Contact

*For questions or collaboration inquiries:*  
**Janhavi S. Ghuge**  
[LinkedIn](https://www.linkedin.com/in/janhavighuge) | [GitHub](https://github.com/janhavighuge)  

---

*This project was completed as part of graduate research at Syracuse University’s The SOURCE lab.*

