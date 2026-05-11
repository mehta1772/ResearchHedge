#  ResearchHedge — Multi-Agent AI Research System with RAG

ResearchMind is an advanced **multi-agent AI system** that performs autonomous research by combining **real-time web search, web scraping, and Retrieval-Augmented Generation (RAG)**.

It mimics a human research workflow — searching, reading, synthesizing, and critically evaluating — but enhances it with **context-aware generation using vector retrieval**.

---

## 🚀 Key Features

* 🔍 **Real-Time Web Search** using Tavily API
* 📄 **Automated Web Scraping** with BeautifulSoup
* 🧠 **RAG (Retrieval-Augmented Generation)** for context-aware responses
* ✍️ **LLM-based Report Generation**
* 🧐 **Self-Critique & Evaluation Chain**
* ⚡ **Multi-Agent Pipeline Architecture**

---

## 🧠 System Architecture

The system follows a **multi-stage AI pipeline enhanced with RAG**, where each component has a dedicated responsibility:

---

### 1️⃣ Search Agent

* Built using **LangChain Agent Executor**
* Tool: `web_search` (Tavily API)
* Fetches **real-time, relevant web data**
* Output stored as: `search_results`

---

### 2️⃣ Reader Agent

* Built using **LangChain Agent Executor**
* Tool: `scrape_url` (BeautifulSoup)
* Extracts **deep, structured content from selected sources**
* Output stored as: `scraped_content`

---

### 3️⃣ RAG Layer (Retrieval-Augmented Generation)

* Converts scraped content into **embeddings**
* Stores data in a **vector store (Pinecone)**
* Retrieves **most relevant context chunks** for the query
* Ensures:

  * Better factual accuracy
  * Reduced hallucination
  * Context-aware generation

---

### 4️⃣ Writer Chain

* Uses:

  * Retrieved context (RAG)
  * Search results
* Generates a **well-structured research report**
* Focus:

  * Depth
  * Clarity
  * Logical flow

---

### 5️⃣ Critic Chain

* Evaluates the generated report
* Provides:

  * Feedback
  * Improvements
  * Quality scoring
* Acts as a **self-review mechanism**

---

## 🔄 Pipeline Flow

```text id="iuz7m0"
User Input (Topic)
        ↓
Search Agent (Tavily API)
        ↓
Reader Agent (Web Scraping)
        ↓
RAG Layer (Embedding + Retrieval)
        ↓
Writer Chain (LLM Report Generation)
        ↓
Critic Chain (Evaluation & Feedback)
        ↓
Final Research Output
```

---

## 🛠️ Tech Stack

* **Frontend:** Streamlit
* **Backend:** Python
* **AI Framework:** LangChain
* **Search API:** Tavily
* **Web Scraping:** BeautifulSoup
* **RAG:** Pinecone (Vector Database)
* **LLM:** OpenAI  models


```bash
cd ResearchAI
uv venv
.venv\Scripts\activate
pip install -r requirements.txt
streamlit run app.py
