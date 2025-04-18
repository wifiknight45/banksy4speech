# banksy4speech
# README for Part-of-Speech Tagger Script

## Overview

This Python script provides a **comprehensive linguistic analysis tool** that combines Part-of-Speech tagging, dependency parsing, named entity recognition, sentiment analysis, and synonym extraction. Using powerful NLP libraries such as **spaCy**, **TextBlob**, and **NLTK**, this script processes a given sentence to generate meaningful insights and saves the results to a file.

---

## Features

### 1. **Part-of-Speech Tagging**
   - Tags each word in a sentence with its part-of-speech (e.g., noun, verb, adjective).
   - Uses the pre-trained `en_core_web_sm` model from spaCy.

### 2. **Dependency Parsing**
   - Provides syntactic roles of words (e.g., subject, object).
   - Displays the relationship between words and their head words.

### 3. **Named Entity Recognition**
   - Identifies entities like names, dates, organizations, and more.
   - Labels entities with categories such as PERSON, DATE, LOCATION, etc.

### 4. **Sentiment Analysis**
   - Analyzes the overall sentiment of the sentence using TextBlob.
   - Measures:
     - **Polarity**: How positive or negative the sentiment is (Scale: -1 to 1).
     - **Subjectivity**: How subjective or objective the sentence is (Scale: 0 to 1).

### 5. **Synonym Extraction**
   - Finds synonyms for each word using the WordNet corpus (NLTK).
   - Displays synonyms to enrich text analysis.

### 6. **Output Results to File**
   - Saves token-level analysis and named entities to `pos_tagger_output.txt`.

---

## Prerequisites

Before running the script, ensure you have the following libraries installed:

1. **spaCy**:
   ```bash
   pip install spacy
   ```
   Also, download the small English model (`en_core_web_sm`) for spaCy:
   ```bash
   python -m spacy download en_core_web_sm
   ```

2. **NLTK**:
   ```bash
   pip install nltk
   ```
   Ensure you download the required resources for NLTK (WordNet):
   ```python
   import nltk
   nltk.download("wordnet")
   ```

3. **TextBlob**:
   ```bash
   pip install textblob
   ```
   If required, download corpora for TextBlob:
   ```bash
   python -m textblob.download_corpora
   ```

---

## How to Use

### 1. **Input Sentence**
   - The script accepts a single sentence or multiple sentences as input.
   - Example:
     ```python
     sentence = "Barack Obama was an outstanding leader loved by many."
     pos_tagger(sentence)
     ```

### 2. **Detailed Analysis**
   - The script will print:
     - POS tags.
     - Dependencies.
     - Lemmas.
     - Named entities.
     - Sentiment metrics.
     - Synonyms for each word.

### 3. **Save Results**
   - The results are saved to a file named `pos_tagger_output.txt`.
   - This file will contain token-level analysis and named entity recognition.

---

## Script Structure

### `pos_tagger(sentence)`
- Main function to process the input sentence.
- Leverages spaCy for POS tagging, dependency parsing, and named entity recognition.
- Calls the `analyze_sentiment` and `save_to_file` functions.

### `get_synonyms(word)`
- Uses NLTK's WordNet corpus to fetch synonyms for a given word.

### `analyze_sentiment(sentence)`
- Utilizes TextBlob to calculate sentiment polarity and subjectivity.

### `save_to_file(doc)`
- Exports analysis results to a text file (`pos_tagger_output.txt`).

---

## Example Output

### Console Output
```plaintext
Detailed Analysis for Each Token:
Word: Barack, POS Tag: PROPN, Dependency: compound, Lemma: barack, Head Word: Obama, Synonyms: N/A
Word: Obama, POS Tag: PROPN, Dependency: ROOT, Lemma: obama, Head Word: Obama, Synonyms: N/A
Word: was, POS Tag: AUX, Dependency: cop, Lemma: be, Head Word: leader, Synonyms: N/A
...

Named Entities in the Sentence:
Entity: Barack Obama, Label: PERSON
Entity: 44th, Label: ORDINAL
Entity: United States, Label: GPE

Sentiment Analysis:
Polarity: 0.8 (Scale: -1 to 1)
Subjectivity: 0.9 (Scale: 0 to 1)

Results saved to 'pos_tagger_output.txt'!
```

### File Output (`pos_tagger_output.txt`)
```plaintext
Word Analysis:
Word: Barack, POS Tag: PROPN, Dependency: compound, Lemma: barack, Head Word: Obama
Word: Obama, POS Tag: PROPN, Dependency: ROOT, Lemma: obama, Head Word: Obama
...

Named Entities:
Entity: Barack Obama, Label: PERSON
Entity: 44th, Label: ORDINAL
Entity: United States, Label: GPE
```

---

## Applications

- **Natural Language Processing (NLP)**:
  - Text preprocessing for machine learning models.
  - Identifying key entities and relationships in text.

- **Sentiment Analysis**:
  - Evaluate customer reviews, social media posts, and feedback.

- **Linguistic Research**:
  - Analyze syntactic structures and semantic relationships.

- **Educational Tools**:
  - Teach language learners about grammar and syntax.

---

## Limitations

- **Contextual Challenges**:
  - Sarcasm and irony may affect sentiment accuracy.
  - Synonym extraction may not always be relevant in certain contexts.

- **Language Support**:
  - Currently optimized for English. Add support for other languages by loading respective spaCy models.

---

## Future Enhancements

- Add multi-language support for POS tagging and sentiment analysis.
- Incorporate deep learning models (e.g., BERT) for sentiment scoring.
- Visualize analysis results using charts or graphs.

---

Acknowlegements: Microsoft Copilot and Google Colab were used to generate this script for the purposes of teaching and learning python for linguistic applications. Feel free to mod out and Happy coding! 🚀
