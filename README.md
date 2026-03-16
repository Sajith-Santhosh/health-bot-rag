# 🧠 Medical Research Paper Explainer (RAG)

A **Retrieval-Augmented Generation (RAG)** system designed to interpret and explain **medical research abstracts** from PubMed with high factual accuracy.

Instead of relying purely on a language model's internal knowledge, this project retrieves **real-world research papers** using semantic search and generates explanations strictly grounded in those scientific sources.

> **Goal:** To demonstrate how modern AI architectures combine **vector databases + LLMs** to mitigate hallucinations and provide evidence-based answers.

---

## ✨ Key Features

* 🔎 **Semantic Search:** Deep contextual search over PubMed abstracts.
* 🧠 **State-of-the-Art Embeddings:** Utilizing BGE-small for high-accuracy retrieval.
* 📚 **Grounded Responses:** Answers are anchored in retrieved literature to prevent AI "hallucinations."
* ⚡ **Lightweight & Fast:** Optimized using a subset of the PubMed dataset for rapid experimentation.
* 🤖 **Advanced LLM Reasoning:** Powered by Google's **Gemma-2-2b-it** for clear, medical-grade explanations.

---

## ⚙️ How It Works

The system follows a standard **RAG Pipeline** to ensure every answer is backed by data:



### The Workflow:
1.  **User Question:** The user submits a medical query.
2.  **Embedding:** The question is converted into a vector using `bge-small-en-v1.5`.
3.  **Vector Search:** **ChromaDB** performs a similarity search to find the most relevant abstracts.
4.  **Context Injection:** The top-ranked abstracts are fed into the LLM as "context."
5.  **Generation:** **Gemma-2-2b-it** synthesizes the final explanation based *only* on the provided research.

---

## 🛠 Technologies Used

| Tool | Purpose |
|:---|:---|
| **Python** | Core programming language |
| **Pandas** | Data loading & preprocessing |
| **SentenceTransformers** | Generating BGE semantic embeddings |
| **ChromaDB** | Vector database for high-speed similarity search |
| **Gemma-2-2b-it** | Large Language Model (LLM) for natural language generation |
| **Hugging Face** | Model hosting and dataset access |

---

## 📊 Dataset

This project utilizes the **PubMed Article Summarization Dataset**. 

* **Source:** Medical research abstracts focusing on clinical studies and trials.
* **Optimization:** For development purposes, the pipeline is configured to use the **first 1,000 abstracts**, ensuring the system remains responsive and lightweight while maintaining a diverse knowledge base.
