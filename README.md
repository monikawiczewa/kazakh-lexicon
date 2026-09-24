# Kazakh Lexicon Generation

**Python NLP pipeline for generating a structured Kazakh-language lexicon from morphologically annotated corpus data**

This project was completed as a **technical language-engineering exercise during a multi-stage recruitment process for a Language Engineer position at the University of Oxford**.

The task was to process a corpus of tokenized and lemmatized Kazakh sentences and generate a structured lexicon containing linguistic and frequency information for each lemma.

## Task

Each token in the supplied corpus was annotated with:

- lemma;
- part-of-speech (POS) label;
- morphological features; and
- surface word form.

The required output was a structured JSON lexicon containing:

- part-of-speech and morphological information;
- total frequency for each lemma; and
- frequency counts for the individual word forms associated with each lemma.

## Implementation

I developed a Python processing pipeline using:

- **Python**
- **Pydantic**
- **pandas**
- **NLTK**
- **JSON**

### 1. Data loading and representation

The pipeline loads the supplied JSON corpus containing tokenized, lemmatized and morphologically annotated sentences.

A Pydantic `TokenData` model is used to represent structured token information including:

- lemma;
- POS label;
- morphological features; and
- word form.

### 2. Linguistic preprocessing

Kazakh stopwords are obtained using NLTK.

Tokens are processed while filtering stopwords and punctuation before valid token information is converted into structured `TokenData` instances.

### 3. Lexicon construction

The processed token data is converted into a pandas DataFrame.

The pipeline then:

1. groups tokens by lemma to calculate total lemma frequencies;
2. groups tokens by lemma and word form to calculate word-form frequencies;
3. combines the resulting linguistic and frequency information; and
4. converts the processed data into the required structured JSON representation.

### 4. Output

The generated lexicon is written to:

`output.json`

The repository also contains sample parsed input data demonstrating the expected corpus structure.

## Repository Contents

- `Kazah_Lexicon_Task.ipynb` — Python implementation and processing pipeline
- `sample_parsed_sentences.json` — sample tokenized and annotated input
- `output.json` — generated structured lexicon
- `README.md` — project documentation

## Engineering Considerations

The exercise also considered how the pipeline could be made more robust for larger-scale use, including:

- validation of input structure;
- error handling for malformed or incomplete data;
- efficient processing of larger corpora; and
- separation of data ingestion, linguistic processing and structured output.

## Context

This repository documents a technical assessment completed during a **University of Oxford Language Engineer recruitment process**.

It represents an independent language-engineering exercise and should not be interpreted as employment by, or a research appointment at, the University of Oxford.

## Author

**Monika Wiczewa**  
Creative Technologist | AI/ML | NLP & Human-Centred AI | Music Technology

[LinkedIn](https://www.linkedin.com/in/monika-wiczewa-9771771a3/)
