# The Monk AI — Advanced RAG Pipeline

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-green.svg)](https://fastapi.tiangolo.com)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.20+-red.svg)](https://streamlit.io)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](https://github.com/Vaibhav13Shukla/The_Monk_AI/blob/main/CONTRIBUTING.md)

A Retrieval-Augmented Generation (RAG) pipeline built on Indian scriptures and spiritual texts, featuring re-ranking, dynamic prompting, voice queries, and multi-turn chat sessions.

## Features

- **Re-ranking**: Cross-Encoder model re-ranks initial search results for higher relevance
- **Dynamic Prompting**: Tailored responses for "beginner" and "expert" modes
- **Multi-Modal Input**: Voice queries via Whisper transcription
- **Post-processing**: Hindi translations, keyword explanations, and book recommendations
- **Session Management**: Persistent chat history with user authentication
- **Modular Architecture**: Clean separation of services, models, and configuration

## Project Structure

```
The_Monk_AI/
├── config/
│   └── config.py          # Centralized configuration
├── data/                  # Scripture JSONL datasets
├── database/
│   └── connection.py      # MongoDB connection management
├── frontend/
│   └── streamlit_app.py   # Web UI
├── models/
│   └── database.py        # Pydantic data models
├── services/
│   ├── auth.py            # User authentication
│   ├── chat_service.py    # Chat session logic
│   ├── document_processor.py
│   ├── llm_service.py     # LLM interactions
│   ├── rag_pipeline.py    # Core RAG orchestration
│   └── vector_store.py    # ChromaDB vector operations
├── main.py                # FastAPI entry point
├── requirements.txt
└── README.md
```

## Quick Start

1. Install dependencies: `pip install -r requirements.txt`
2. Set up environment variables in `.env`
3. Initialize the vector database
4. Run the backend: `uvicorn main:app --reload`
5. Launch the frontend: `streamlit run frontend/streamlit_app.py`

## Architecture

The pipeline retrieves relevant scripture passages using vector similarity search, re-ranks them with a Cross-Encoder, and generates responses via Groq API. Responses are enriched with Hindi translations and contextual explanations based on the user's selected mode.

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | FastAPI, Python 3.8+ |
| Frontend | Streamlit |
| Vector DB | ChromaDB |
| LLM | Groq API (LLaMA, Mixtral) |
| Embeddings | HuggingFace Transformers |
| Re-ranking | CrossEncoder |
| Database | MongoDB (motor) |
| Auth | JWT, passlib |
