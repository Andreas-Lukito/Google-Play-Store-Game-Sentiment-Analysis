# Google Play Game Reviews Sentiment Analysis

## Overview
This project evaluates two machine learning models—**XGBoost Classifier** and **LSTM**—for sentiment classification on Google Play game reviews.  
Two text representation methods were used: **TF-IDF** and **Word2Vec**, with a dataset limited to **1000 samples**.

## Results
| Data | Word Embedding Method | Model | Weighted Precision | Weighted Recall | Weighted F1 Score |
| ---- | --------------------- | ----- | ------------------ | --------------- | ----------------- |
| Balanced | TF-IDF | XGB Classifier | 0.20 | 0.19 | 0.19 |
| Balanced | Word2Vec | XGB Classifier | 0.20 | 0.19 | 0.19 |
| <b style="color:green">Balanced</b> | <b style="color:green">TF-IDF</b> | <b style="color:green">LSTM</b> | <b style="color:green">0.50</b> | <b style="color:green">0.46</b> | <b style="color:green">0.32</b> |
| Balanced | Word2Vec | LSTM | 0.0625 | 0.25 | 0.10 |
| Imbalanced | TF-IDF | XGB Classifier | 0.23 | 0.23 | 0.23 |
| Imbalanced | Word2Vec | XGB Classifier | 0.18 | 0.19 | 0.18 |
| <b style="color:green">Imbalanced</b> | <b style="color:green">TF-IDF | <b style="color:green">LSTM | <b style="color:green">0.50 | <b style="color:green">0.44 | <b style="color:green">0.45 |
| Imbalanced | Word2Vec | LSTM | 0.063 | 0.25 | 0.10 |

**Results Discussion:**
- The best-performing model is <b style="color:green">TF-IDF + LSTM</b>, with a weighted F1-score of **0.32** on balanced data and **0.45** on imbalanced data.  
- The overall results are relatively low, which is **expected** due to the <b style="color:red">1000-sample data limit</b>, making it challenging for models to fully learn sentiment patterns.  
- Balancing the dataset did **not dramatically** affect the results. Suggesting that <b style="color:red">dataset size</b>, rather than imbalance, is the main performance bottleneck.  
- The results also indicate that the **text preprocessing pipeline** is effective in:
  - Cleaning noisy and unstructured text data  
  - Reducing bias from frequent or non-informative words  
  - Helping the model focus on **meaningful sentiment cues** rather than class frequency  
- As a result, even with **uneven label distribution**, the model was still able to <b style="color:green">generalize sentiment patterns</b> reasonably well.