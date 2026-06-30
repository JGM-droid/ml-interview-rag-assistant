# Machine Learning Interview RAG Assistant

This project is a Retrieval-Augmented Generation (RAG) knowledge assistant built for machine learning and data science interview preparation.

The assistant retrieves relevant information from a custom knowledge base and uses that context to answer technical interview questions about machine learning fundamentals, preprocessing, feature engineering, model evaluation, neural networks, computer vision, NLP, embeddings, and RAG systems.

## Project Goal

The goal is to build a complete RAG pipeline that can:

- Load custom knowledge-base documents
- Chunk documents into retrievable sections
- Generate embeddings
- Store embeddings in ChromaDB
- Retrieve relevant chunks for a user query
- Generate answers using retrieved context
- Support junior data scientists preparing for technical interviews

## Project Scenario

**Scenario:** Study Guide  
**Topic:** Machine Learning and Data Science Interview Assistant

Target users include:

- Junior Data Scientists
- TripleTen students
- Bootcamp graduates
- Career changers preparing for ML interviews

## Repository Structure

```text
Jesse_Montemayor_FinalRAG_Project/

├── final_RAG_project.ipynb
├── README.md
├── requirements.txt
│
├── docs/
│   ├── Machine_Learning_Fundamentals_and_Data_Science_Workflow.md
│   └── Data_Preprocessing.md
│
└── chroma_db/