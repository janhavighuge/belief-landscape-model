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

🔁 End-to-End Project Flow: Reddit NLP Pipeline (r/climate)
📥 Data Collection

Scraped 1M+ posts from r/climate using Pushshift API

Captured post content, metadata, and engagement signals (e.g., score, comments)

🧹 Preprocessing

Cleaned and tokenized text (retained case + demojized emojis)

Removed noise: URLs, special characters, common stopwords

Preserved features like capitalization, emoji sentiment, and post timing

📊 Feature Engineering

Extracted TF-IDF vectors and Word2Vec embeddings

Added metadata-based features (e.g., post length, flair, caps ratio)

Created custom emotion/sentiment scores using VADER and NRC lexicon

🧠 Topic Modeling + User Intent Segmentation

Used BERTopic and weak supervision (keywords, flairs)

Tuned K-Means, DBSCAN, and Hierarchical clustering

Achieved 85% accuracy in labeling posts into segments like activism, denial, policy

📈 Sentiment Analysis (Enhanced)

Combined VADER with custom LSTM + GloVe model

Improved classification accuracy by 15% on 100K manually tagged posts

⚠️ Behavioral Risk Signal Detection

Labeled posts with weak supervision into risk categories (e.g., hostility, hopelessness)

Trained classifiers (Random Forest, Logistic Regression) on these tags

🚀 Deployment

Built and deployed a Flask app on Google Cloud Platform

Automated ingestion + prediction pipelines to handle 400K+ posts/day
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

