# GraphRAG-E-Commerce-Assistant

Built a GraphRAG (Graph Retrieval-Augmented Generation) pipeline that combines Neo4j knowledge graph traversal with vector similarity search to answer natural language product queries. The system uses HuggingFace embeddings for semantic search, Groq LLM for dynamic Cypher query generation, and Neo4j for structured graph enrichment — enabling relationship-aware answers that go beyond what traditional RAG can provide. For example, querying a brand returns not just its products but also related categories, ratings, and alternatives discovered through graph traversal.
Tech Stack: Python, Neo4j, LangChain, Groq, HuggingFace Transformers


install these libraries 
!pip install -q langchain langchain-groq langchain-community neo4j sentence-transformers python-dotenv

# 🛍️ GraphRAG for E-Commerce — Knowledge Graph + RAG Pipeline

> **Stack:** Neo4j · Groq (LLaMA-3) · HuggingFace Embeddings · LangChain

## What This Project Does
This notebook builds a **GraphRAG system** for an e-commerce product catalog. It combines:
- **Neo4j** as a graph database to store products, categories, brands, and their relationships
- **HuggingFace Embeddings** for semantic vector search
- **Groq (LLaMA-3)** to generate Cypher queries from natural language *and* to answer questions
- **Graph Traversal** to enrich RAG context with related nodes (brand → products, category → subcategories)

## Architecture
```
User Question
     │
     ├──► Groq: Generate Cypher Query ──► Neo4j Graph Traversal ──┐
     │                                                             ├──► Merged Context ──► Groq: Final Answer
     └──► HuggingFace: Vector Search  ──► Semantic Results ───────┘
```

## Setup Requirements
```
pip install langchain langchain-groq langchain-community neo4j sentence-transformers python-dotenv
```
You'll need:
- `GROQ_API_KEY` → https://console.groq.com
- `NEO4J_URI`, `NEO4J_USERNAME`, `NEO4J_PASSWORD` → https://neo4j.com/cloud/platform/aura-graph-database (free tier)




