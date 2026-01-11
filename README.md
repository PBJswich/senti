# Stock Sentiment Scorer (FinBERT)

A specialized Python utility that performs financial sentiment analysis on news articles. Unlike general-purpose NLP tools, this uses **FinBERT**, a language model specifically trained on financial corpora (like earnings reports and analyst statements) to provide more accurate market signals.

## Features
* **Financial Specialization:** Uses the `ProsusAI/finbert` model for context-aware sentiment analysis.
* **Weighted Scoring:** Translates model confidence into a custom **-10 (Strongly Bearish)** to **+10 (Strongly Bullish)** scale.
* **Confidence Breakdown:** Provides a percentage-based breakdown of Bullish, Bearish, and Neutral probabilities.
* **Multi-line Input:** Supports pasting full articles directly into the terminal.

## Installation

### 1. Clone the repository
```bash
git clone [https://github.com/yourusername/stock-sentiment-scorer.git](https://github.com/yourusername/stock-sentiment-scorer.git)
cd stock-sentiment-scorer 
```

### 2. Install Dependencies
#### This project requires Python 3.8+ and the following libraries:

```bash
pip install torch transformers
```
Note: The first time you run the script, it will download approximately 400MB of model weights from Hugging Face.

## Usage
### Run the script from your terminal:
```bash
python sentiment_scorer.py
```

#### 1. When prompted, paste the text of the news article.

#### 2. Press Enter twice to signal the end of the text.

#### 3. The script will process the text and return the sentiment report.

## Scoring Logic

``` 
Score = (Probability_Positive - Probability_Negative) * 10 
```

## Limitations
* ***Input Length***: The model is optimized for 512 tokens (roughly 400 words). Longer articles will be truncated to the first 512 tokens.

* ***Hardware***: This runs on CPU by default. For bulk processing of hundreds of articles, a GPU is recommended.
