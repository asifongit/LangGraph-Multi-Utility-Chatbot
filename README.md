# LangGraph Multi-Utility Chatbot

A conversational AI chatbot built with **LangGraph** and **Streamlit**. It supports multi-turn chat with memory, PDF question-answering, web search, stock price lookup, and a calculator — all in one interface.

---

![Project Screenshot](assets/screenshot.png)

## What It Does

- **Chat with memory** — each conversation is saved and can be resumed later
- **PDF Q&A** — upload a PDF and ask questions about it
- **Web search** — searches the web via DuckDuckGo when needed
- **Stock prices** — fetches live stock data (e.g. AAPL, GOOGL)
- **Calculator** — handles basic math operations
- **Named conversations** — chats are automatically named from your first message and stored persistently

---

## Tech Stack

| Layer | Tool |
|---|---|
| LLM | Groq (LLaMA / GPT-OSS) |
| Embeddings | OpenAI `text-embedding-3-small` |
| Orchestration | LangGraph |
| Memory / Checkpointing | SQLite (`chatbot.db`) |
| Vector Store | FAISS |
| UI | Streamlit |

---

## Project Structure

```

langgraph_backend.py    # Core logic: LLM, tools, graph, DB 
langgraph_frontend.py   # Streamlit UI
chatbot.db                  # Auto-created SQLite database (chat history + names)
.env                        # API keys (not committed)
```

---

## Setup

**1. Clone the repo and create a virtual environment**
```bash
git clone https://github.com/asifongit/LangGraph-Multi-Utility-Chatbot.git
python -m venv venv
venv\Scripts\activate        # Windows
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Add your API keys** — update  `.env` file:
```
GROQ_API_KEY=your_groq_key
OPENAI_API_KEY=your_openai_key
```

**4. Run the app**
```bash
streamlit run langgraph_frontend.py
```

---

## How to Use

1. Open the app in your browser (`http://localhost:8501`)
2. Type a message to start chatting — the first message becomes the chat name
3. To ask about a PDF, upload it from the sidebar first
4. Click **New Chat** to start a fresh conversation
5. Past conversations appear in the sidebar — click any to resume

