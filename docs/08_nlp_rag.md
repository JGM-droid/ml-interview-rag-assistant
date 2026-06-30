# Natural Language Processing, Embeddings & Retrieval-Augmented Generation (RAG)

## What is Natural Language Processing (NLP)?

Natural Language Processing (NLP) is a branch of Artificial Intelligence that enables computers to understand, interpret, and generate human language.

Unlike structured data such as numbers stored in spreadsheets, human language is unstructured and contains ambiguity, slang, grammar, context, and multiple meanings for the same word. NLP combines machine learning, linguistics, and statistics to help computers process written and spoken language.

Common NLP applications include:

- Chatbots and virtual assistants
- Machine translation
- Sentiment analysis
- Spam detection
- Search engines
- Text summarization
- Question answering systems
- Large Language Models (LLMs)

---

# Why NLP is Challenging

Human language is complex.

For example, the word **bank** can mean:

- A financial institution
- The side of a river

Humans easily understand the correct meaning based on context, but computers must learn these relationships from data.

Other NLP challenges include:

- Synonyms
- Misspellings
- Abbreviations
- Sarcasm
- Multiple languages
- Context-dependent meanings

---

# Text Preprocessing

Before text can be used in machine learning models, it usually undergoes preprocessing.

Common preprocessing steps include:

- Convert text to lowercase
- Remove punctuation
- Remove extra whitespace
- Tokenization
- Remove stop words
- Lemmatization

Preprocessing reduces noise and improves the quality of text representations.

---

# Tokenization

Tokenization is the process of breaking text into smaller pieces called tokens.

Example:

```
Machine learning is amazing.
```

↓

```
["Machine", "learning", "is", "amazing"]
```

Tokens may represent:

- Words
- Characters
- Subwords

Modern transformer models commonly use subword tokenization.

---

# Stop Words

Stop words are common words that usually carry little meaning.

Examples include:

- the
- and
- is
- of
- to

Removing stop words often improves traditional NLP models by reducing unnecessary information.

---

# Lemmatization vs Stemming

Both techniques reduce words to a simpler form.

## Lemmatization

Uses vocabulary and grammar rules to produce real dictionary words.

Example:

```
Running

↓

Run
```

---

## Stemming

Simply removes word endings.

Example:

```
Running

↓

Runn
```

Lemmatization generally produces more meaningful text and is commonly preferred for modern NLP tasks.

---

# Traditional NLP Methods

Before deep learning became popular, text was represented using frequency-based methods.

Common techniques include:

- Bag of Words (BoW)
- CountVectorizer
- TF-IDF
- N-grams

These methods work well for many simple classification problems but struggle to understand meaning and context.

---

# Bag of Words (BoW)

Bag of Words represents text by counting how often each word appears.

Example:

Sentence:

```
Dogs chase cats.
```

↓

```
Dogs: 1
Cats: 1
Chase: 1
```

Advantages:

- Simple
- Fast
- Easy to understand

Limitations:

- Ignores word order
- Ignores context
- Produces sparse feature vectors

---

# TF-IDF

TF-IDF stands for **Term Frequency – Inverse Document Frequency**.

Instead of simply counting words, TF-IDF gives higher importance to words that are unique within a collection of documents.

Common words receive lower weights, while informative words receive higher weights.

TF-IDF is widely used for:

- Search
- Document ranking
- Text classification

---

# Word Embeddings

Traditional NLP methods represent words as counts.

Embeddings represent words as dense numerical vectors that capture semantic meaning.

Example:

```
Dog

↓

[0.12, -0.48, 0.91, ...]
```

Words with similar meanings have similar vectors.

Examples:

- Dog
- Puppy
- Canine

These words appear close together within the embedding space.

---

# Static Embeddings

Static embedding models assign one vector to each word.

Examples include:

- Word2Vec
- GloVe
- FastText

Limitation:

The word **bank** receives the same vector regardless of context.

Example:

```
The bank approved my loan.

The boat reached the bank.
```

Static embeddings cannot distinguish between these meanings.

---

# Contextual Embeddings

Modern transformer models generate embeddings based on context.

The meaning of a word changes depending on surrounding words.

Examples include:

- BERT
- RoBERTa
- Sentence Transformers

Contextual embeddings produce significantly better language understanding than static embeddings.

---

# Sentence Embeddings

Instead of embedding individual words, sentence embeddings represent the meaning of an entire sentence.

Example:

```
How do I prevent overfitting?
```

↓

Dense numerical vector

Sentence embeddings are commonly used for:

- Semantic search
- Question answering
- Retrieval-Augmented Generation

---

# Semantic Search

Traditional keyword search only finds exact word matches.

Semantic search retrieves documents based on meaning rather than exact wording.

Example:

User searches:

```
automobile
```

Document contains:

```
car
```

Keyword search may fail.

Semantic search recognizes that both words have similar meanings and retrieves the correct document.

---

# Vector Databases

Embeddings must be stored efficiently for similarity search.

Vector databases are designed specifically for storing and searching embedding vectors.

Popular vector databases include:

- ChromaDB
- Pinecone
- FAISS
- Weaviate
- Milvus

Unlike relational databases, vector databases search by similarity rather than exact values.

---

# Similarity Search

Similarity search compares embedding vectors to find the most relevant documents.

A common similarity metric is **Cosine Similarity**.

Cosine Similarity measures how closely two vectors point in the same direction.

Higher similarity indicates greater semantic meaning.

---

# Document Chunking

Large documents are typically divided into smaller sections called chunks.

Chunking improves retrieval because smaller pieces of information are easier to match with user queries.

Good chunking balances:

- Context
- Retrieval accuracy
- Search speed

Chunks that are too small lose important context.

Chunks that are too large may retrieve unnecessary information.

---

# What is Retrieval-Augmented Generation (RAG)?

Retrieval-Augmented Generation (RAG) combines a Large Language Model with an external knowledge base.

Instead of relying only on information learned during training, the system first retrieves relevant documents and then uses those documents as context when generating an answer.

This approach produces responses that are more accurate, more relevant, and grounded in external information.

---

# The RAG Pipeline

A typical Retrieval-Augmented Generation workflow consists of the following steps:

1. Create knowledge base documents.
2. Split documents into chunks.
3. Generate embeddings for each chunk.
4. Store embeddings in a vector database.
5. Convert the user's question into an embedding.
6. Perform similarity search.
7. Retrieve the most relevant document chunks.
8. Send the retrieved context to a Large Language Model.
9. Generate a grounded response.

---

# Advantages of RAG

Compared to using a Large Language Model by itself, RAG provides several benefits:

- More accurate answers
- Reduced hallucinations
- Domain-specific knowledge
- Easier knowledge updates
- No need to retrain the model when documents change

---

# Limitations of RAG

Although powerful, RAG systems also have limitations.

Performance depends on:

- Document quality
- Chunking strategy
- Embedding model
- Retrieval accuracy
- Knowledge base completeness

Poor retrieval leads to poor answers, even when the language model itself is strong.

---

# This Project's RAG Workflow

This project follows a complete Retrieval-Augmented Generation pipeline.

The workflow is:

```
Markdown Documents

↓

Document Chunking

↓

Sentence Transformer Embeddings

↓

ChromaDB Vector Database

↓

Semantic Similarity Search

↓

Retrieved Context

↓

Large Language Model

↓

Grounded Response
```

Instead of answering from memory alone, the assistant retrieves relevant interview knowledge before generating a response.

---

# Common Interview Questions

Interviewers frequently ask:

- What is NLP?
- What is tokenization?
- Why remove stop words?
- What is TF-IDF?
- What are embeddings?
- What is the difference between Word2Vec and BERT?
- What is semantic search?
- What is a vector database?
- Why use ChromaDB?
- What is document chunking?
- Why is chunk size important?
- What is Retrieval-Augmented Generation?
- Why use RAG instead of fine-tuning?
- How does a RAG pipeline work?

Strong interview answers explain both the technical concepts and the practical benefits of retrieval-based AI systems.

---

# Key Takeaways

- NLP enables computers to understand and generate human language.
- Text preprocessing improves the quality of textual data before modeling.
- TF-IDF measures word importance, while embeddings capture semantic meaning.
- Contextual embeddings outperform traditional static embeddings because they understand context.
- Semantic search retrieves information based on meaning rather than exact keywords.
- Vector databases store embeddings for efficient similarity search.
- Retrieval-Augmented Generation combines semantic retrieval with Large Language Models to produce accurate, grounded responses.
- A well-designed knowledge base is the foundation of an effective RAG system.