![[RAG Systems 2025-03-21 19.43.02.excalidraw]]
## 🧠 Retriever: What It Actually Does

The **retriever** is like the "memory" for your LLM. Since LLMs don’t know your custom data (PDFs, Notion notes, databases, etc.), the retriever is what pulls in relevant chunks from that data.

It’s basically a **semantic search engine**.

### 🔄 Step-by-Step: How a Retriever Works

1. ### 📚 Data Preprocessing (Once)
    
    - Split your documents into **chunks** (e.g., paragraphs, 500-token windows).
    - Each chunk gets **embedded** into a vector using an embedding model (like `text-embedding-ada-002` from OpenAI or `sentence-transformers`).
    - Store these vectors in a **vector database** (e.g., FAISS, Pinecone, Weaviate).
    
2. ### 🧭 At Query Time (Every time user asks something)
    
    - User types a query → Embed it into a vector (same embedding model as above).
    - Compare it to all vectors in your database using **cosine similarity** or similar.
    - Retrieve top-k most similar chunks = the most semantically related pieces of text.
    - Those chunks go to the LLM as context for answering.
### Embeddings = Meaning Vectors

- Instead of keyword matching like traditional search, embeddings capture **semantic meaning**.
    - “How to bake a cake” and “cake recipe steps” might be **very similar** in vector space.
- So even if your query and a doc use **different wording**, the retriever can still find it.