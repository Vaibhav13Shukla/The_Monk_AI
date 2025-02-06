# The Monk AI — Advanced RAG Pipeline

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
