# Spam SMS Detection - CodSoft ML Internship Task 4

My submission for Task 4 of the CodSoft Machine Learning internship.

## What this does

Classifies SMS messages as spam or legit (ham) based on the text content.

## Dataset

SMS Spam Collection dataset from Kaggle:
https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset

About 5500 messages labeled ham or spam. The csv has some extra unnamed columns and uses latin-1 encoding so had to handle that when loading it.

Download the csv from the link above (usually named `spam.csv`) and put it in this folder before running.

## What I did

- Cleaned the text - lowercased everything, removed urls, punctuation, and numbers
- Converted text to TF-IDF vectors (capped at 3000 features so the matrix doesn't get too huge)
- Tried three models: Naive Bayes, Logistic Regression, and Linear SVM
- Compared them on accuracy, precision, recall, f1-score
- Ran a few made up test messages through the model just to sanity check it actually works on new text, not just memorizing the test set

## Files

- `spam_detection.py` - main script
- `generate_sample_data.py` - makes fake sms data to test the code without needing the real dataset first
- `requirements.txt`

## How to run

```
pip install -r requirements.txt
python spam_detection.py
```

## Results

All three models did well on this dataset, TF-IDF already captures a lot since spam messages have pretty distinct vocabulary (free, win, claim, urgent, click here etc). Linear SVM had the best recall for spam in my testing which matters here since missing an actual spam message is worse than a false alarm.

---
Santanu Mondal
B.Tech CSE (AI & ML), Adamas University

Done as part of the CodSoft Machine Learning internship, Sept 2026.
