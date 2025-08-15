# 🔍 AI_RAG_Assistant (FAISS + OpenAI)

A lightweight RAG (Retrieval-Augmented Generation) assistant that lets you ask questions about any uploaded document using OpenAI + FAISS. Built entirely in Google Colab.

## ✅ Features

- Upload any `.txt` document
- Split into chunks for processing
- Generate embeddings via `text-embedding-3-small`
- Store embeddings in FAISS index
- Search top-k similar chunks

## 📦 Tech Stack

- OpenAI Python SDK (`openai`)
- FAISS (`faiss-cpu`)
- Google Colab (no deployment needed)

## 🚀 How to Use

1. Run in Google Colab
2. Upload a `.txt` file
3. Wait for FAISS index to build
4. Ask questions like:
   - "What are the main products of this company?"
   - "When was the service launched?"
   - "List all key features."

## 🧠 Example
Q: What does the company provide?  
A: According to the document, they offer...  
