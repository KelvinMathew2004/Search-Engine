# Googol 🔎

## 🔗 Project URL
https://userweb.cs.txstate.edu/~dha25/index.html

---

## 📌 Overview
This project implements a **Single-Page Application (SPA)** search engine that runs entirely on the client side.  
It is designed to be hosted directly on a university Linux environment (`public_html`) without requiring backend servers or special installation permissions.

---

## ⚙️ Implementation Details

### 🏗️ Architecture & Security
- Fully client-side SPA architecture (no backend required)
- API keys are stored in a separate `config.js` file
- Environment variables are dynamically imported at runtime to keep the codebase clean and modular

---

### 🌐 Part A: Web Search
- Integrated **Google Custom Search API** for primary search functionality
- Implemented a **fault-tolerant fallback system**:
  - Automatically switches to **Wikipedia Web Search API** if:
    - API quota is exceeded
    - Google API fails
- Built UI using **Tailwind CSS**, styled to resemble modern search engines
- Application is branded as **"Googol"**
- Implemented full **pagination system** for sequential result fetching

---

### 📂 Part B: Local Search
- Implemented local search using:
  - `lunr.js` (client-side search engine based on Lucene)
  - `PapaParse` (CSV parsing)
- Workflow:
  1. Load `lyrics.csv` dataset on page load
  2. Build an **inverted index** in browser memory
  3. Perform fast local searches using Lunr

- Advanced Features:
  - Generated **KWIC (Keyword-In-Context)** snippets using positional metadata
  - Implemented **custom pagination system**:
    - Lunr returns all results at once
    - Cached results in a JavaScript array
    - Displayed results in a smooth **10-per-page UI**

---

## 💡 Observations & Insights
- Moving Lucene-style search (**Lunr**) to the client side eliminates the need for backend infrastructure
- Successfully deployed entirely on a university Linux account without requiring services like Apache or Elasticsearch
- Demonstrates that:
  - Client-side architecture can handle **robust information retrieval**
  - Features like **pagination, indexing, and fault tolerance** can be effectively implemented without a server

---

## 🚀 Key Takeaways
- Fully serverless search application
- Fault-tolerant multi-source search system
- Efficient in-browser indexing and querying
- Clean, modular, and portable deployment

---
