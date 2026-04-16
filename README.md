# Emotion-Based Recipe Recommendation System

An NLP-powered dual-model system that detects emotion from user text and recommends recipes based on detected mood and calorie preferences.

## Results

| Model | Metric | Score |
|-------|--------|-------|
| Emotion Classifier (BiLSTM) | Test Accuracy | 92.87% |
| Emotion Classifier (BiLSTM) | Weighted F1-Score | 0.93 |
| Recipe Recommender (Attention BiLSTM) | Test MAE | 0.189 |
| Recipe Recommender (Attention BiLSTM) | RMSE | 0.243 |

## How It Works

**Model 1 — Emotion Classifier:**
- Takes free text input from the user
- Classifies text into 9 emotions: anger, happiness, love, sadness, hate, relief, neutral, fun, enthusiasm
- Built with BiLSTM architecture, trained on 80,000 samples

**Model 2 — Recipe Recommender:**
- Uses emotion detected by Model 1 as input
- Filters recommendations based on user calorie constraints
- Built with Attention-based BiLSTM trained on emotion-labelled recipe reviews

**Pipeline Innovation:**
Model 1 was applied to pseudo-label the recipe review dataset, creating emotion annotations for Model 2 training — a literature-grounded transfer approach.

## Tech Stack

- Python, TensorFlow, Keras
- NLTK, NumPy, Pandas
- Scikit-learn, Matplotlib, Seaborn
- Trained on Kaggle (GPU: T4)

## Model Performance Detail

**Per-class F1 scores (Emotion Classifier):**

| Emotion | Precision | Recall | F1 |
|---------|-----------|--------|----|
| Love | 0.97 | 0.98 | 0.97 |
| Sadness | 0.99 | 0.94 | 0.97 |
| Hate | 1.00 | 0.87 | 0.93 |
| Relief | 0.95 | 0.95 | 0.95 |
| Happiness | 0.94 | 0.96 | 0.95 |
| Neutral | 0.93 | 0.88 | 0.90 |
| Anger | 0.99 | 0.82 | 0.90 |
| Enthusiasm | 0.80 | 0.97 | 0.87 |
| Fun | 0.70 | 0.95 | 0.80 |

## Author

Mohammed Nihal Thonikkara — MSc Artificial Intelligence, National College of Ireland
[LinkedIn](https://www.linkedin.com/in/mohammed-nihal-thonikkara)
