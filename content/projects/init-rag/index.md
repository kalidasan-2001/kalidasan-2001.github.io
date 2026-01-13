---
title: 'inIT-RAG: LLM-Powered Knowledge Base System'
summary: 'A production RAG system that crawls websites and enables semantic search with local LLMs, featuring web crawler, vector storage, and interactive chat interface for the inIT Institute.'
tags:
  - AI/ML
  - RAG
  - LLM
  - Web Crawling
  - Python
  - LlamaIndex
date: '2025-11-01'
external_link: 'https://github.com/kalidasan-2001/inIT-RAG'

image:
  caption: 'inIT-RAG Chatbot Interface'
  focal_point: Smart

links:
  - icon: brands/github
    name: View Code
    url: 'https://github.com/kalidasan-2001/inIT-RAG'

url_code: 'https://github.com/kalidasan-2001/inIT-RAG'
---

## Overview

inIT-RAG is a **Retrieval-Augmented Generation (RAG)** chatbot designed for the Parkinson's PD Assistant App at the inIT Institute. The system crawls websites, indexes content using vector embeddings, and provides accurate Q&A with source citations using local LLM models.

**Current Implementation:** Indexed 4,622 pages from init-owl.de with 16,405 text chunks totaling 214MB.

## Key Features

### Ìµ∑Ô∏è Advanced Web Crawler
- Recursive crawling with configurable depth control
- Domain filtering and robots.txt compliance
- PDF document processing with text extraction
- Clean content extraction using Trafilatura
- Duplicate detection and URL normalization

### Ì≥ö Vector Storage & Retrieval
- Semantic search using HuggingFace embeddings (all-MiniLM-L6-v2)
- LlamaIndex for document orchestration
- 1024-token chunks with 200-token overlap
- Top-5 similarity-based retrieval

### Ì¥ñ Local LLM Integration
- **Ollama** integration (Gemma2:2b model)
- Completely free and offline operation
- Context-aware response generation
- Source citation with URLs

### Ì≤¨ Web Interface
- Clean Flask-based chat UI
- Dark/light theme toggle
- Real-time streaming responses
- Source link display for answers
- Responsive design

## Architecture

### Data Pipeline
```
Web Crawler ‚Üí Content Extraction ‚Üí Text Chunking ‚Üí 
Vector Embedding ‚Üí Storage ‚Üí Retrieval Engine ‚Üí LLM ‚Üí Web UI
```

### Technical Components
1. **Crawler Module**: Trafilatura + Beautiful Soup for content extraction
2. **Vector Store**: HuggingFace embeddings with LlamaIndex
3. **LLM Engine**: Ollama (Gemma2:2b) for local inference
4. **Web UI**: Flask server with modern chat interface

## Technical Stack

- **Framework**: LlamaIndex for RAG orchestration
- **LLM**: Ollama (Gemma2:2b) - local, free
- **Embeddings**: HuggingFace (sentence-transformers/all-MiniLM-L6-v2)
- **Web Crawling**: Trafilatura, Beautiful Soup, Requests
- **Backend**: Flask, Flask-CORS
- **Storage**: JSON-based vector store (214MB for 4,622 pages)
- **PDF Processing**: PDFReader from llama-index

## Performance Metrics

- **Startup Time**: 60-90 seconds (one-time loading)
- **Query Response**: 2-5 seconds (vector search + LLM generation)
- **Memory Usage**: 2-3GB idle, ~4GB during queries
- **Indexed Content**: 4,622 pages, 16,405 chunks
- **Storage Size**: 214MB (141MB vectors + 72MB text)

## Key Achievements

‚úÖ Successfully implemented end-to-end RAG pipeline  
‚úÖ Achieved offline operation with local models (zero API costs)  
‚úÖ Built responsive web interface with theme support  
‚úÖ Implemented efficient chunking strategy for context retrieval  
‚úÖ Integrated source citation for answer transparency  

## Use Cases

- **Research Assistant**: Query institute documentation and research
- **Information Retrieval**: Find specific information across large websites
- **Document QA**: Ask questions about website content
- **Knowledge Management**: Centralized access to institutional knowledge

## Configuration

### Crawler Settings
```python
CrawlConfig(
    base_url="https://www.init-owl.de",
    max_depth=3,        # Link depth
    max_pages=5000,     # Max pages to crawl
    delay=0.5,          # Polite crawling
)
```

### Chunk Settings
```python
Settings.node_parser = SentenceSplitter(
    chunk_size=1024,     # Tokens per chunk
    chunk_overlap=200    # Context overlap
)
```

## Future Enhancements

- Incremental index updates (avoid full re-crawling)
- Multi-modal support (images, tables)
- Conversation history and follow-up questions
- Advanced evaluation metrics (RAGAS, context relevance)
- Production deployment with WSGI server
- Markdown rendering in chat responses

---

**Technologies**: Python, LlamaIndex, Ollama, HuggingFace, Flask, Trafilatura, Beautiful Soup, Vector Search
