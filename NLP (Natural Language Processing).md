# NLP (Natural Language Processing)

## Definition

**NLP (Natural Language Processing)** is the field that enables computers to understand, analyze, generate, and use human language.

**Main challenges**:

- Ambiguity in language  
- Strong dependence on context  
- Large amount of implicit knowledge  
- The same sentence can have different meanings in different scenarios  

---

## Two Main Categories of Tasks

### 1. Understanding Tasks

- **Text Classification**
  
  - Sentiment Analysis (positive / negative)
  - Topic Classification (sports / finance / entertainment)

- **Sequence Labeling**
  
  - Token labeling (word segmentation, NER)
  - Named Entity Recognition (person, location, organization)
  - Example:  
    - Beijing / University / Zhang San → Location / Organization / Person

- **Sentence-Level Relations**
  
  - Natural Language Inference (NLI): entailment / contradiction / neutral
  - Semantic similarity matching

- **Information Extraction**
  
  - Extract *entity–relation–attribute* triples from text  
  - Example:  
    - “Elon Musk founded SpaceX” → (Elon Musk, founded, SpaceX)

- **Reading Comprehension / Question Answering**
  
  - Answer questions based on a given passage

---

### 2. Generation Tasks

- **Machine Translation**: Chinese ↔ English
- **Summarization**: extractive / abstractive
- **Dialogue Systems**: customer service bots, chat assistants
- **Writing Assistance**: rewriting, grammar correction, continuation

---

## Basic NLP Pipeline

### 1. Text Preprocessing

- **Tokenization**
  - Split raw text into tokens that models can process
  - Example:  
    - “I love natural language processing” → I / love / natural / language / processing

---

### 2. Text Representation

- **One-Hot Encoding**
  
  - Each word is represented as a vector with one `1` and all other positions `0`
  - Vocabulary: `["I", "like", "learning"]`
    - “I” → [1, 0, 0]  
    - “like” → [0, 1, 0]
  - Pros: simple and intuitive  
  - Cons: high dimensional, no semantic information

- **Bag of Words (BoW)**
  
  - Counts word frequency and ignores word order
  - Sentence: “I like learning learning”  
    - {I:1, like:1, learning:2} → [1, 1, 2]
  - More informative than one-hot  
  - Loses word order  
  - (“I hit you” and “you hit I” are treated the same)

- **TF-IDF**
  
  - Words are important if they:
    - Appear frequently in a document (high TF)
    - Appear rarely in the whole corpus (high IDF)
  - More reasonable than BoW  
  - Still sparse and lacks semantic understanding

- **Word Embeddings**
  
  - Dense, low-dimensional vector representations
  - Semantically similar words are closer in vector space
  - Distance ≈ semantic similarity (cosine similarity)
  - Example method: Word2Vec
  - Captures semantic and contextual information

---

### 3. Modeling

Use mathematical models or neural networks to learn language patterns.

- **Traditional Statistical Models**
  
  - Naive Bayes, HMM

- **Machine Learning Models**
  
  - SVM, Logistic Regression

- **Deep Learning Models**
  
  - RNN / LSTM
  - CNN for text

- **Transformer (Core of Modern NLP)**
  
  - Self-attention mechanism
  
  - Highly parallelizable
  
  - **Encoder-Only Models (Strong Understanding)**
    
    - BERT family
    - Suitable for: classification, NER, extraction
    - Training objective: Masked Language Modeling (MLM)
  
  - **Decoder-Only Models (Strong Generation)**
    
    - GPT family
    - Suitable for: continuation, dialogue, text generation
    - Training objective: autoregressive next-token prediction
  
  - **Encoder–Decoder Models (Strong Translation & Summarization)**
    
    - T5, BART family
    - Suitable for: translation, summarization, conditional generation

---

### 4. Output

- Classification labels
- Probabilities
- Generated text
- Translated sentences

---

## Evaluation Metrics

### 1. Classification

- Precision
- Recall
- F1-score

### 2. Generation (Translation / Summarization / Dialogue)

- **BLEU (Translation)**
  
  - Measures n-gram overlap between prediction and reference
  - Higher is better (1–4 grams)

- **ROUGE (Summarization)**
  
  - Measures how many reference n-grams are covered by the system summary

- **Perplexity (PPL)**
  
  - Measures uncertainty in language model predictions
  - Lower PPL → better predictive ability

- **NDCG (Ranking)**
  
  - Measures whether more relevant items are ranked higher
