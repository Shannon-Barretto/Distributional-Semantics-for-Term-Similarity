# Distributional Semantics for Term Similarity

## Project Overview

This project explores distributional semantics to estimate the similarity between pairs of terms using a large Wikipedia-based text corpus. The primary objective is to implement and evaluate sparse and dense semantic representations to compute cosine similarity scores for given term pairs.

## Tasks

### Task 1: Sparse Representation

* Approach: Bag-of-Words (BoW) with TF-IDF.

* Vectorization: TF-IDF vectorizer with trigrams, min_df=5, max_df=0.3.

* Preprocessing:
  * Lowercasing
  * Removal of punctuation, digits, newlines, URLs, HTML tags, and square brackets
  * Tokenization using NLTK
  * Stop word removal (NLTK's stop word list)

* Similarity Calculation:
  * Cosine similarity between vectors of term pairs
  * Multi-word terms handled by averaging pairwise token similarities
  * OOV (Out-of-Vocabulary) words default to similarity 0.5

### Task 2: Dense Representation

* Approach: Word2Vec (Skip-gram model)
* Implementation: Gensim Word2Vec
* Training Data: Cleaned and tokenized WikiText-103 corpus
* Preprocessing:
  * Same steps as Task 1 with additional lemmatization
* Model Parameters:
  * Size: 100 dimensions
  * Window size: 5
  * min_count: 5
  * sg=1 (Skip-gram)

* Similarity Calculation:
  * Cosine similarity between word vectors
  * Multi-word terms represented by average of individual word vectors
  * OOV words default to similarity 0.5
 
## Notes
* All representations were built from scratch using the provided WikiText-103 corpus.
* No pre-trained word vectors were used.
* Multi-word terms and OOV handling were explicitly addressed.
