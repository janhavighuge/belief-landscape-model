# belief-landscape-model

🎯 Objective
To understand how misinformation, sentiment, and belief dynamics spread across Reddit — specifically within the climate discourse — using scalable Natural Language Processing and Machine Learning techniques. The ultimate goal was to detect misinformation patterns, topic polarization, and behavioral risk signals in real-time.

🔁 Project Overview
“We developed an end-to-end NLP pipeline that ingested 1M+ Reddit posts, processed and enriched text data, applied machine learning models for topic/sentiment analysis, detected behavioral risk markers, and visualized shifts in user intent — all deployed via a Flask web app on GCP.”

🧱 Pipeline Architecture
1. Data Collection
Used Pushshift API to scrape over 1M Reddit posts from r/climate and related subreddits.

Collected post body, title, timestamp, author, flair, upvotes, and comment count.

2. Preprocessing
Tokenization, URL/email removal, punctuation stripping.

Emoji conversion using emoji and demojize to retain emotional context.

Preserved capitalization and used it as a feature, rather than lowercasing (since uppercase often reflects emotional intensity).

Removed stopwords but retained domain-relevant words (e.g., “climate,” “CO2”).

3. Feature Engineering
TF-IDF for sparse keyword features.

Word2Vec and GloVe embeddings to capture semantic context.

Incorporated metadata features: post length, caps ratio, time of post, flair.

Extracted emotions using NRC Emotion Lexicon and VADER for sentiment.

🔍 4A. Topic Modeling & Intent Segmentation
“We wanted to understand what people were talking about — activism, skepticism, scientific debate, or denial — and how those topics evolved over time.”

Used BERTopic for unsupervised topic modeling.

Cleaned output using reclustering, topic merging, and manual labeling.

Labeled 30+ topics such as:

Climate Denialism

Policy and Regulation Debates

Activism and Protests

Tech Solutions (EVs, Solar, etc.)

Climate Anxiety

🔖 Weak Supervision for Intent
Labeled topics into macro-intents like Activism, Denial, Debate, Supportive, using:

Keywords (e.g., “hoax”, “march”, “fossil fuel”)

Subreddit flairs (if available)

Sentence context

💬 4B. Sentiment Analysis
Used VADER for rule-based sentiment scoring.

Applied custom LSTM + GloVe to improve sentiment classification accuracy by 15%.

Fine-tuned on 100K manually reviewed Reddit posts using scikit-learn + TensorFlow.

Visualized sentiment trends over time with topic overlays.

🧠 5. Behavioral Risk Signal Detection
“We engineered behavioral features to catch when users shifted from skepticism to hostility or hopelessness — markers of belief escalation or distress.”

Defined risk categories: Hostility, Hopelessness, Conspiratorial, Crisis, Activism.

Used weak supervision: keywords, caps usage, sentence structure, flairs.

Features included:

Caps ratio, punctuation stress (!!!)

Emotion scores (anger, fear, sadness)

Post timing (e.g., late night posting spikes)

Trained Logistic Regression and Random Forests with class-balancing for multi-class classification.

Achieved ~78% F1 score on risky vs non-risky content.

🧠 Risk Clustering:
Embedded posts via UMAP and Word2Vec, clustered via KMeans + HDBSCAN.

Identified “hot spots” of escalating conspiratorial sentiment or radical call-to-actions.

🚀 6. Deployment
“To make this useful for ongoing monitoring, we operationalized it via a live web app.”

Built a Flask web app to serve predictions and risk visuals.

Deployed on Google Cloud Platform using App Engine and Cloud Storage.

Automated ingestion + scoring pipeline handling 400K+ posts/day.

Enabled researchers to:

Query recent risk signals

Monitor trending topics

Track belief shifts in near real-time

📈 Impact
✅ Improved sentiment classification accuracy by 15%
✅ Segmented user intents with 85% clustering accuracy
✅ Detected early warning signs of belief polarization and misinformation spread
✅ Enabled real-time insights into community shifts and behavioral risk dynamics
✅ Positioned the platform for future integration with misinformation response teams

🧰 Tech Stack
Category	Tools Used
Languages	Python, HTML/CSS (Flask app)
Libraries	Scikit-learn, BERTopic, TensorFlow, NLTK, VADER, Gensim, UMAP, HDBSCAN
Deployment	Flask, Google Cloud Platform (App Engine, Cloud Storage)
Data Ingestion	Pushshift API
Visualization	Matplotlib, Seaborn, Plotly

