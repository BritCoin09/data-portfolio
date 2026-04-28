# Project 14 — IMDB Sentiment Classification (NLP)

## Machine Learning for Texts: Classifying Movie Reviews

📌 ### Project Overview

This project builds a machine‑learning model to classify IMDB movie reviews as positive or negative.
The Film Junky Union wants to automatically detect negative reviews to support content moderation and improve user experience.

The dataset includes labeled reviews already split into train and test sets.

**Goal:**

Achieve an F1 score ≥ 0.85 on the test set using NLP preprocessing and multiple ML models.

🧠 ### Key Skills Demonstrated

- Natural Language Processing (NLP)

- Text normalization & preprocessing

- TF‑IDF vectorization (unigrams + bigrams)

- Logistic Regression & LightGBM

- Model evaluation (F1, ROC AUC, PRC, APS)

- Error analysis & feature importance

- Pipeline thinking & real‑world ML workflow

📂 ### Project Structure

- imdb_sentiment.ipynb — full notebook with EDA, preprocessing, modeling, and evaluation

- data/ — IMDB reviews dataset (train/test split provided)

- README.md — project summary

🔍 ### Exploratory Data Analysis (EDA)

**Before modeling, I explored:**

- Movie release trends over time

- Positive vs. negative review distribution

- Review count anomalies (e.g., spike at exactly 30 reviews)

- Class balance (dataset is nearly 50/50)

This helped validate data quality and understand potential modeling challenges.

🛠️ ### Preprocessing

**All reviews were normalized:**

- Lowercasing

- Removing punctuation & digits

- Collapsing extra spaces

- Optional: stopword removal (NLTK)

- Optional: lemmatization (spaCy)

- Vectorization used TF‑IDF with up to 50,000 features.

🤖 ### Models Tested

- Model 1 — TF‑IDF + Logistic Regression (NLTK stopwords)
F1 (test): 0.88  
ROC AUC: 0.95

- Model 2 — TF‑IDF + Logistic Regression (no stopwords)
F1 (test): 0.88  
ROC AUC: 0.95

- Model 3 — spaCy Lemmatization + TF‑IDF + Logistic Regression
F1 (test): 0.88  
ROC AUC: 0.95

- Model 4 — spaCy Lemmatization + TF‑IDF + LightGBM
F1 (test): 0.87  
ROC AUC: 0.94  
(High overfitting)

📊 ### Model Comparison

Model	Preprocessing	Algorithm	Test F1	ROC AUC	Overfitting
Model 1	NLTK stopwords	Logistic Regression	0.88	0.95	Low
Model 2	Basic TF‑IDF	Logistic Regression	0.88	0.95	Low
Model 3	spaCy lemmatization	Logistic Regression	0.88	0.95	Low
Model 4	spaCy lemmatization	LightGBM	0.87	0.94	High


**Best choice: Logistic Regression (Model 1–3)**

🔎 ### Error Analysis

**I examined misclassified reviews to understand model behavior:**

- False positives: overly enthusiastic language in otherwise negative reviews

- False negatives: subtle positive sentiment or mixed reviews

This helps identify future improvements (e.g., sentiment lexicons, transformers).

🧩 ### Feature Importance (LightGBM)

**Top sentiment‑driving words included:**

- good, great, excellent, wonderful

- bad, awful, boring, waste

These align with human intuition and validate model interpretability.

🧪 ### Testing on Custom Reviews

I ran predictions on 10 manually written reviews to evaluate real‑world behavior.

**The model correctly identified:**

- sarcasm

- boredom

- enthusiasm

- mixed sentiment

This demonstrates strong generalization.

✅ ### Final Result

**The final model achieved:**

F1 Score: 0.88

ROC AUC: 0.95

APS: 0.95

This performs reliably on unseen text.