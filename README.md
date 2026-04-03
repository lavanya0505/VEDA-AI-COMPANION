# VEDA — AI Mental Health Companion

A full-stack AI system designed to provide emotionally aware, context-sensitive conversational support. VEDA focuses on presence, reflection, and grounded dialogue using local LLM inference and optional retrieval augmentation.

---

## Overview

VEDA is an AI-powered conversational system built to simulate calm, human-like interactions during emotionally heavy or reflective moments. The system prioritizes contextual understanding, low-latency interaction, and privacy through local model execution.

---

## Architecture

```
Frontend (React + Vite)
        ↓
FastAPI Backend (/chat endpoint)
        ↓
Conversation Engine (prompt + session memory)
        ↓
Local LLM (Ollama - Mistral)
        ↓
Response returned to UI
```

---

## Key Features

- Context-aware conversational responses  
- Session-based memory (no authentication required)  
- Local LLM inference via Ollama (no external API dependency)  
- Optional Retrieval-Augmented Generation (RAG) pipeline  
- Modular backend architecture for extensibility  
- Lightweight and responsive frontend interface  

---

## Tech Stack

| Layer        | Technology                     |
|-------------|-------------------------------|
| Frontend     | React, Vite, Tailwind CSS     |
| Backend      | FastAPI                       |
| LLM Runtime  | Ollama (Mistral)              |
| Language     | Python, TypeScript            |
| RAG (Optional)| Custom vectorstore pipeline  |

---

## System Design

- Frontend handles UI and user interaction only  
- Backend manages all logic, prompting, and memory  
- LLM runs locally for privacy and cost efficiency  
- Memory is session-scoped and non-persistent  
- RAG integrates contextual retrieval when enabled  

---

## Setup

### Prerequisites
- Python 3.10+
- Node.js 18+
- Ollama installed → https://ollama.com

---

### Installation

```bash
git clone https://github.com/lavanya0505/VEDA-AI-COMPANION.git
cd VEDA-AI-COMPANION
```

---

### Backend Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

---

### Install Model

```bash
ollama pull mistral
```

---

### Run Backend

```bash
uvicorn main:app --reload
```

---

### Run Frontend

```bash
cd Frontend/veda
npm install
npm run dev
```

---

## Session Memory

- Each session is assigned a unique session ID  
- Memory persists only during active session  
- No user accounts or stored personal data  
- Stateless reset on session end  

---

## Retrieval-Augmented Generation (Optional)

- Enables contextual grounding via vectorstore  
- Injects relevant context into prompt pipeline  
- Designed to be non-intrusive and fallback-safe  

---

## Performance

- Initial response latency: ~2–3 seconds  
- Subsequent responses: ~1–2 seconds  
- Optimized for stability and conversational flow  

---

## Safety Considerations

- No medical or diagnostic claims  
- Non-authoritative responses  
- Designed for general conversational support  
- Not a substitute for professional help  

---

## Development Notes

- Core logic implemented in `engine.py`  
- API layer kept minimal (`main.py`)  
- Frontend contains no model logic  
- LLM backend is easily swappable  

---

