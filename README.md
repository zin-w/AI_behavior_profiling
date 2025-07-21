# AI Personality Profiling from Text using MBTI

A full end-to-end NLP project that analyzes and predicts MBTI (Myers-Briggs Type Indicator) personality types based on user-generated text. This project includes EDA, NLP preprocessing, clustering, classification, and deployment via FastAPI.

---

## Dataset

- **Source:** [Kaggle - MBTI Personality Dataset](https://www.kaggle.com/datasnaek/mbti-type)
- **Rows:** 8,675
- **Columns:** 
  - `type` — One of 16 MBTI personality types (e.g., INFP, ESTJ)
  - `posts` — User text data compiled from multiple posts

---

## Project Structure

| Stage | Description |
|-------|-------------|
| **Data Loading** | Imported dataset via `kagglehub` and loaded with pandas |
| **Preprocessing** | Removed URLs, MBTI labels, and tokenized post blocks |
| **Feature Engineering** | TF-IDF, sentiment analysis, word count, pronouns, average word length |
| **Exploratory Analysis** | Top keywords per type, sentiment by MBTI, WordClouds |
| **Clustering** | KMeans and graph-based clustering using cosine similarity |
| **Modeling** | Naive Bayes, Logistic Regression, and binary trait classifiers (IE, NS, FT, PJ) |

---

## Results

### Full 16-Type Classifier (Logistic Regression)
- **Accuracy:** 66%
- Strong predictions for dominant types (INFP, INTP)
- Underperforms on rare types (e.g., ESFJ, ESTJ)

### Binary Trait Classifiers
| Trait | Accuracy |
|-------|----------|
| I/E   | 69% |
| N/S   | 72% |
| F/T   | 76% |
| P/J   | 64% |

Binary classification improves balance and interpretability.

---

## Key Visualizations

- Top keywords per MBTI via TF-IDF
- WordClouds of high-frequency words
- Sentiment analysis by type
- Social Graph of user similarities (based on cosine similarity)
- Behavioral clusters via PCA and Truncated SVD

---
## License

MIT License. See LICENSE file for details.
___

## Contact

- Created by Suchada W.
- Email: suchadawongkot1@gmail.com
- GitHub: zin-w

Feel free to fork, raise issues, or submit pull requests!

___

### Endpoint:
```bash
POST /predict
