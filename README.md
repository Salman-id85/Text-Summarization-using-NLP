# Text-Summarization-using-NLP


This project implements a Text Summarization tool using Natural Language Processing (NLP) techniques. The tool processes input text from various sources, calculates the Term Frequency-Inverse Document Frequency (TF-IDF) for words, scores sentences, and generates a summary based on the sentence scores.

---

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Functions](#functions)
- [Example](#example)
- [License](#license)

---

## Introduction

The primary goal of this project is to extract the most important sentences from a given text and present them in a concise summary. The summarization process utilizes TF-IDF to calculate the importance of words in sentences, and sentences are scored accordingly.

---

## Features

- **Text Input Options**: 
  - Type or paste text directly.
  - Load text from `.txt` files.
  - Load text from `.pdf` files.
  - Fetch and summarize Wikipedia articles.

- **Text Processing**:
  - Frequency matrix generation.
  - Term Frequency (TF) and Inverse Document Frequency (IDF) calculations.
  - TF-IDF matrix creation.
  - Sentence scoring and summarization.

- **Customizable Thresholds**: Adjust the threshold to control the length and detail of the summary.

---

## Installation

1. **Clone Repository**:
   ```
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Install Dependencies**:
   Install the required libraries by running:
   ```
   pip install -r requirements.txt
   ```

3. **Download NLTK Data**:
   ```
   python -c "import nltk; nltk.download('wordnet')"
   ```

4. **Download spaCy Model**:
   ```
   python -m spacy download en_core_web_sm
   ```

---

## How to Use

1. **Run the Script**:
   ```
   python summarizer.py
   ```

2. **Select Input Source**:
   Choose one of the following options for input:
   - Type or copy-paste text.
   - Load text from a `.txt` file.
   - Load text from a `.pdf` file.
   - Enter a Wikipedia URL to summarize an article.

3. **Generated Summary**:
   The program will display the summarized text and statistics about the original and summarized text.

---

## Functions

### 1. Reading Input
- `file_text(filepath)`: Reads `.txt` files.
- `pdfReader(pdf_path)`: Reads `.pdf` files.
- `wiki_text(url)`: Reads Wikipedia articles.

### 2. Frequency and Scoring
- `frequency_matrix(sentences)`: Generates a frequency matrix for words in sentences.
- `tf_matrix(freq_matrix)`: Calculates Term Frequency for words.
- `sentences_per_words(freq_matrix)`: Determines the number of sentences containing each word.
- `idf_matrix(freq_matrix, sent_per_words, total_sentences)`: Calculates Inverse Document Frequency.
- `tf_idf_matrix(tf_matrix, idf_matrix)`: Combines TF and IDF to compute TF-IDF scores.
- `score_sentences(tf_idf_matrix)`: Scores sentences based on TF-IDF.

### 3. Summarization
- `average_score(sentence_score)`: Calculates the average sentence score.
- `create_summary(sentences, sentence_score, threshold)`: Generates a summary based on the sentence scores.

---

## Example

**Input**:
> A lengthy text from a file, Wikipedia article, or custom input.

**Output**:
- A summarized version of the text.
- Statistics:
  - Total words in the original text.
  - Total words in the summarized text.
