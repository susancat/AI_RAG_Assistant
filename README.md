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

## Lambda Deploymeng
💡 For those looking to scale beyond notebooks, this assistant can also be deployed as an AWS Lambda container. Here’s the general idea:  
Instead of running in a notebook, you can package the Python code (including FAISS index + OpenAI calls) inside a lightweight Docker container.  
This container is then uploaded to AWS Elastic Container Registry (ECR) and deployed to Lambda with custom resource limits.  
Once deployed, you get a serverless REST endpoint (via API Gateway) that lets you send a user query (e.g., {"query": "which products the company has？"}) and receive an AI-generated answer — instantly and on-demand.  

The FAISS index and document chunks are preloaded into the container, enabling fast vector search even in a stateless serverless environment.  
This pattern allows for:  
- 💡Zero infrastructure management
- 📦 Reusable container image
- ⚡️ Fast cold-start time (especially when using small models like text-embedding-3-small)
- 💰 Pay-per-use, making it cost-efficient for lightweight query workloads

Still fine-tuning the container and permission setup (AWS has some nuances!), but this workflow shows how even simple prototypes can evolve into scalable, production-ready APIs.  
