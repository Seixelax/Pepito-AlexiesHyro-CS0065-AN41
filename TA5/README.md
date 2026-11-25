# TA5: Lexicon-Based & Polarity Sentiment Analysis Engine

## 📌 Project Overview
This repository contains a two-stage Natural Language Processing (NLP) sentiment analysis pipeline developed for CS0065 (Intelligent Systems). The implementation contrasts statistical lexicon-based polarity/subjectivity scoring via `TextBlob` against a deterministic, token-level affective counting model (`number_happy` vs. `number_sad`) for sentence-level tone classification.

## 🧮 Algorithmic Methodology

The system evaluates unstructured text data through two distinct sentiment extraction workflows:

### 1. Continuous Polarity & Subjectivity Analysis (Batch Engine)
- **Architecture:** Pre-trained Lexical Polarity Classifier (`TextBlob`).
- **Function:** Ingests a 10-sentence batch stream and computes continuous sentiment polarity ($p \in [-1.0, 1.0]$) alongside subjectivity scores ($s \in [0.0, 1.0]$).
- **Classification & Aggregation:** Maps continuous polarity outputs into discrete sentiment classes ($p < 0$: Negative, $p = 0$: Neutral, $p > 0$: Positive) and aggregates class distribution counts across the evaluation batch.

### 2. Token-Level Affective Lexicon Model (Challenge Engine)
- **Architecture:** Regex-Tokenized Set-Lookup Classifier (`number_happy` and `number_sad`).
- **Tokenization:** Normalizes input strings to lowercase and extracts alphabetic tokens via regular expressions (`[a-z']+`) to eliminate punctuation noise.
- **Decision Logic:** Evaluates token membership against curated positive and negative affective lexicons, classifying overall sentence tone (`happy`, `sad`, or `neutral`) by comparing relative affective token frequencies.

## 📂 Repository Structure
- **TA5_Sentiment_Analysis.ipynb:** The self-contained Colab notebook containing the `TextBlob` batch evaluator, regex tokenizer, affective lexicon sets, and tone classification functions.
- **TA5_PEPITO.pdf:** The compiled laboratory report detailing the methodology, test cases, and execution screenshots.

## 🚀 Execution

The script relies on standard Python libraries (`re`) and `textblob`.

1. Execute the batch evaluation cell and input 10 test sentences when prompted to generate polarity scores and the overall distribution summary.
2. Execute the affective lexicon cell and input a target sentence to compute happy/sad token counts and classify tone.

## 👤 Author
- [**Alexies Hyro Pepito**](https://github.com/Seixelax)
