# UCSD Data Mining 256

Coursework for UC San Diego's DSE 256 (Data Mining and Analytics). It covers recommender-system prediction tasks and an end-to-end classification and text-regression project on Rent the Runway clothing reviews.

## Repository Contents

| File | Description |
|---|---|
| `assignment1.ipynb` | Assignment 1: read prediction and rating prediction for user–book pairs |
| `writeup.txt` | Short write-up of the approach used in Assignment 1 |
| `Assignment 2.ipynb` | Assignment 2: Rent the Runway fit classification and review-text models |
| `alex hayslip assignment 2 final report.pdf` | Final report for Assignment 2 |

## Commit History

### `b96c57c`: Assignment 2 notebook and final report (2025-09-05)
- **Added the files:** `Assignment 2.ipynb` and the final report PDF.
- **Dataset:** Rent the Runway clothing-fit reviews (192,544 reviews), from Julian McAuley's UCSD dataset collection.
- **Cleaning:**
  - dropped nulls and duplicates
  - converted age and rating to integers
  - removed units from bust size and weight and converted them to numbers
- **EDA findings:**
  - ratings are heavily skewed toward high scores, averaging just over 9 out of 10
  - the most common rental occasions
- **Classification:** a multi-class logistic regression with balanced class weights predicts `fit` from bust size, weight, age, size and total inches. Accuracy was about 52% (balanced error rate ≈ 0.47), and tuning the regularization strength `C` barely changed it.
- **Text regression on review text, predicting rating:**
  - bag of words with the 2,000 most common words: MSE 1.90
  - adding stemming: MSE 2.11 (worse)
  - keeping stop words: MSE 1.94
  - TF-IDF features
  - a regularized pipeline: MSE 1.91 at C = 0.1
- **Wrap-up:** summarized related academic research on fashion recommender systems, and conclusions for each model.

### `be9d5ba`: Assignment 1 notebook (2025-09-05)
- **Added `assignment1.ipynb`.**
- **Read prediction:** predicts whether a user read a given book, using Jaccard similarity and a generated set of negative (unread) examples.
- **Rating prediction:** predicts star ratings for user–item pairs with a latent factor model (a global average plus user and item bias terms), fit with gradient descent and regularization.

### `a5dd5e7`: Write-up for Data Mining 256 (2026-01-04)
- **Added `writeup.txt`:** a short explanation of the strategy for each Assignment 1 task.

## Tools
Python, pandas, NumPy, SciPy, scikit-learn, NLTK, matplotlib, seaborn, Jupyter Notebook
