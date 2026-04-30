# 🤖 Resume Chatbot using n8n (RAG-based AI Assistant)

## 📌 Overview

This project is an AI-powered chatbot built using n8n that allows users to upload a resume (PDF) and interact with it conversationally.

It uses a **Retrieval-Augmented Generation (RAG)** pipeline to extract, store, and query resume data efficiently.

---

## 🚀 Features

* 📄 Upload resume via form (PDF)
* 🧠 Extract and process resume content
* 🔍 Semantic search using vector embeddings
* 💬 Chat with your resume using AI
* 🧾 Context-aware responses with memory
* ⚡ Fast retrieval using Pinecone vector database

---

## 🧠 Tech Stack

* **n8n** – Workflow automation
* **OpenAI** – LLM + embeddings
* **Pinecone** – Vector database
* **LangChain (n8n nodes)** – AI orchestration

---

## 🏗️ Architecture

```text
          ┌──────────────┐
          │ Resume Upload│
          └──────┬───────┘
                 ↓
        ┌──────────────────┐
        │ Text Extraction  │
        └──────┬───────────┘
               ↓
        ┌──────────────────┐
        │ Embeddings (AI)  │
        └──────┬───────────┘
               ↓
        ┌──────────────────┐
        │ Pinecone Vector  │
        │ Database         │
        └──────┬───────────┘

User Query → AI Agent → Vector Search → Response
```

---

## ⚙️ Workflow Breakdown

### 📥 Resume Processing Pipeline

1. **Form Trigger**

   * Accepts resume upload (PDF)

2. **Default Data Loader**

   * Extracts text from the PDF

3. **Embeddings (OpenAI)**

   * Converts text into vector embeddings

4. **Pinecone Vector Store**

   * Stores embeddings for semantic retrieval

---

### 💬 Chatbot Pipeline

1. **Chat Trigger**

   * Receives user queries

2. **AI Agent**

   * Handles reasoning and tool usage

3. **OpenAI Chat Model**

   * Generates responses (`gpt-4.1-mini`)

4. **Simple Memory**

   * Maintains conversation context

5. **Vector Store Tool**

   * Retrieves relevant resume chunks

---

## 🔄 How It Works

1. User uploads a resume
2. Resume text is extracted and processed
3. Text is converted into embeddings
4. Embeddings are stored in Pinecone
5. User asks questions
6. AI retrieves relevant information
7. AI generates contextual answers

---

## 🛠️ Setup Instructions

### 1. Import Workflow

* Open n8n
* Import `workflows/chatbot.json`

### 2. Configure Credentials

* Add your OpenAI API key
* Add your Pinecone API key

### 3. Configure Pinecone

* Create an index (e.g., `n8n-demo`)
* Ensure dimensions match embedding model

### 4. Run the Workflow

* Activate workflow
* Upload a resume via form
* Start chatting via webhook


Built using n8n and modern AI tools as part of hands-on learning in agentic workflows and RAG systems.
