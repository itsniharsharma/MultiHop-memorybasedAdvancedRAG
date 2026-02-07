# MultiHop-memorybasedAdvancedRAG

# 🕉️ Multi-Hop Hinglish Gita RAG Chatbot

A Multi-Hop Retrieval Augmented Generation (RAG) chatbot built on the **Bhagavad Gita**, designed to answer spiritual and life questions in **friendly Hinglish**, using grounded verse-level retrieval, reasoning hops, and conversational memory.

Built fully in a notebook environment (Kaggle-compatible) without heavy backend infrastructure.

---

# 🚀 Features

- ✅ Verse-level Bhagavad Gita chunking
- ✅ Semantic embeddings using SentenceTransformers
- ✅ Pinecone vector database indexing
- ✅ Multi-hop reasoning retrieval
- ✅ Query decomposition using LLM
- ✅ Cross-encoder reranking
- ✅ Context-grounded generation
- ✅ Hinglish conversational answers
- ✅ GPT-style line-by-line output (no paragraph walls)
- ✅ Friendly “dost-style” tone
- ✅ Shloka/verse reference included
- ✅ Chat memory support
- ✅ Gradio chat UI
- ✅ Kaggle notebook compatible

---

# 🧠 System Architecture

```
Bhagavad Gita PDF
↓
Verse Marker Parsing (chapter.verse)
↓
Sub-chunking
↓
SentenceTransformer Embeddings
↓
Pinecone Vector DB Index

User Query
↓
Query Decomposition (LLM)
↓
Multi-Hop Retrieval
↓
Passage Reranking
↓
Context Merge + Chat Memory
↓
Final Hinglish LLM Generation
↓
Gradio Chat Interface
```

---

# 📦 Tech Stack

- Python
- SentenceTransformers (all-mpnet-base-v2)
- Pinecone Vector Database
- Groq / LLaMA LLM API
- Gradio
- PyPDF
- Regex parsing
- LangChain utilities (optional helpers)

---

# 🔍 Retrieval Design

## Verse-Level Chunking
- Parsed Gita PDF
- Extracted `(chapter.verse)` markers
- Built structured chunks
- Sub-chunked long passages for embedding quality

## Multi-Hop RAG Flow
The system:
1. Breaks user question into sub-questions
2. Retrieves context per sub-query
3. Merges evidence
4. Reranks passages
5. Generates grounded Hinglish answer

---

# 💬 Response Style

The assistant responds in:

- Hinglish (Roman Hindi + English)
- Friendly conversational tone
- Line-by-line GPT chat format
- Bullet-style readable output
- Verse references included
- Follow-up question asked
- Strictly grounded in retrieved context

Example output style:

```
• Krishna yahan senses control ki baat karte hain (2.58)

• Matlab — senses withdraw kar pao to mind stable hota hai

• Stable mind → karma yoga strong hota hai

Tumhe distraction zyada kis type ke situations me aata hai?
```

---

# 🧾 Memory Support

## Short-Term Memory
- Uses Gradio chat history
- Injected into final prompt
- Maintains conversational continuity

## Long-Term Memory (Extendable)
- Separate Pinecone namespace possible
- Can store personal notes / user context
- Enables personalized guidance mode

---

# 🛠️ Setup

## 1️⃣ Install Dependencies

```
pip install pinecone sentence-transformers pypdf gradio groq
```

---

## 2️⃣ Set API Keys

Set as environment variables or Kaggle Secrets:

```
PINECONE_API_KEY=your_key
GROQ_API_KEY=your_key
```

---

## 3️⃣ Data Preparation

- Upload Bhagavad Gita PDF
- Run chunking + parsing notebook cells
- Generate embeddings
- Upsert vectors to Pinecone index

---

## 4️⃣ Run Chat UI

```python
gr.ChatInterface(fn=chat_fn).launch()
```

---

# 📂 Suggested Repo Structure

```
/notebooks
    rag_pipeline.ipynb

/data
    gita_chunks.json

/src
    chunking.py
    retrieval.py
    multihop.py
    llm_answer.py

README.md
requirements.txt
```

---

# ⚠️ Guardrails

- Answers restricted to retrieved context
- No out-of-context verse claims
- Explicit fallback when answer missing
- Tone + format enforced via prompt rules

---

# 🔮 Future Improvements

- Exact verse citation from metadata
- Dual-namespace personal + scripture RAG
- Auto memory extraction
- Reflection journaling mode
- Multi-text expansion
- Evaluation benchmarks
- Streaming token output
- API deployment layer

---

# 👤 Author

Experimental spiritual + reasoning RAG system combining:
AI retrieval, multi-hop reasoning, and conversational UX design.

---

# 📜 License

MIT License — free to use and extend.

---

# ⭐ If You Like This Project

Star the repo and build your own domain RAG systems.
Spiritual texts + AI reasoning is just getting started.
