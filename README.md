# Ohrid Sentiment Analysis

Comparative analysis of machine learning models for sentiment analysis of tourist reviews in Ohrid, North Macedonia.

This repository accompanies a research paper submitted to **ICT Innovations 2026**. It compares four sentiment analysis approaches spanning three generations of NLP methods, applied to a novel dataset of tourist reviews from a UNESCO World Heritage destination.

## Overview

The study addresses two questions:

1. Which model best classifies the sentiment (positive / neutral / negative) of tourist reviews?
2. How does sentiment vary across different tourism service domains (attractions, restaurants, hotels)?

Four models are compared:

| Model | Type |
|-------|------|
| VADER | Lexicon-based |
| Naive Bayes | Classical machine learning |
| Logistic Regression | Classical machine learning |
| RoBERTa | Transformer-based deep learning |

## Dataset

`DataOhrid_FINAL.xlsx` contains **1,060 tourist reviews** collected manually from publicly available TripAdvisor reviews for academic research purposes. Reviews span three domains:

- **Attractions** — churches, fortress, national park, ancient theatre, and other cultural and natural sites
- **Restaurants**
- **Hotels**

Sentiment labels are derived from star ratings (4–5★ = positive, 3★ = neutral, 1–2★ = negative). The dataset was balanced across sentiment classes to enable a fair comparison between models.

## Methodology

- Text preprocessing (lowercasing, removal of non-letter characters)
- TF-IDF feature extraction (max 5,000 features)
- Model training and evaluation using accuracy, precision, recall, and F1-score
- 5-fold cross-validation for robustness
- Confusion matrix analysis
- Secondary analysis: sentiment distribution by domain

## Results

Single train/test split (80/20, stratified):

| Model | Accuracy | Neutral F1 |
|-------|----------|------------|
| VADER | 0.59 | 0.12 |
| Naive Bayes | 0.68 | 0.31 |
| Logistic Regression | **0.71** | **0.50** |
| RoBERTa | 0.67 | 0.26 |

Logistic Regression achieved the highest accuracy on the single split. Five-fold cross-validation showed the traditional models (Naive Bayes and Logistic Regression) performing comparably. The neutral class proved the most challenging to classify across all models.

Domain-level analysis showed attractions receiving the most positive reviews, while restaurants received the most critical feedback.

## Repository Structure

| File | Description |
|------|-------------|
| `Ohrid_Sentiment_Analysis.ipynb` | Main notebook with all code and analysis |
| `DataOhrid_FINAL.xlsx` | Dataset of 1,060 labeled tourist reviews |
| `README.md` | Project documentation |

## How to Run

1. Open `Ohrid_Sentiment_Analysis.ipynb` in [Google Colab](https://colab.research.google.com/)
2. Upload `DataOhrid_FINAL.xlsx`
3. Run all cells (**Runtime → Run all**)

### Dependencies

- pandas
- scikit-learn
- vaderSentiment
- transformers
- matplotlib

## Author

**Andrea Lekoska**

BSc in Information Systems, Faculty of Computer Science and Engineering,
Ss. Cyril and Methodius University, Skopje, North Macedonia

This work was developed as part of a research paper submitted to ICT Innovations 2026.
