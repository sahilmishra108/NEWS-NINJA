# 🧠 NewsNinja – AI Journalist using MCP, RAG & TTS

**NewsNinja** is your personal AI-powered journalist that fetches, summarizes, and narrates the latest from premium **News** sources and **Reddit** discussions. It combines web scraping via **BrightData MCP**, summarization via **Anthropic Claude / Ollama**, and **Text-to-Speech** generation using ElevenLabs or gTTS.

## 📌 Key Features

- 🔍 Scrape real-time news from Google News using BrightData MCP
- 📑 Analyze Reddit reactions using LangChain agents
- 🧠 Summarize content using Anthropic Claude / Ollama
- 🎙️ Generate human-like audio summaries (via ElevenLabs or gTTS)
- ⚡ Fully modular backend + Streamlit-based frontend
- 🔄 Uses Model Context Protocol (MCP) for tool chaining

---

## 📂 Project Structure

| File/Folder                | Description                                      |
|----------------------------|--------------------------------------------------|
| 📁 `NewsNinja/`            | Root project directory                           |
| ├── `frontend.py`          | Streamlit UI for topic selection + playback      |
| ├── `news_scraper.py`      | Scrapes Google News results via BrightData MCP   |
| ├── `reddit_scraper.py`    | Scrapes Reddit and analyzes sentiment            |
| ├── `models.py`            | Pydantic model for API validation                |
| ├── `utils.py`             | Utility functions for scraping, TTS, summarizing |
| ├── `Pipfile` / `Pipfile.lock` | Pipenv environment files                  |
| ├── `README.md`            | Project documentation                            |
| ├── `.env` (not included)  | Environment variables                            |
| └── `audio/`               | Generated audio files                            |

---

## 🧱 Core Technologies

- **Streamlit** – UI for topic input and playback
- **FastAPI** – (optional) Backend API
- **BrightData MCP** – Browser-based scraping
- **LangChain Agents** – Tool chaining and summarization
- **Anthropic Claude** – Summarization LLM
- **Ollama** – Local LLM summarizer
- **ElevenLabs / gTTS** – Text-to-speech generation
- **Python Async + Tenacity** – Retry logic for scraping

---

## 📐 Architecture

### Phase 1 – Frontend Interaction

- Select topic and source (News, Reddit, or Both)
- Click “Generate Summary”
- Streamlit sends POST request to backend

### Phase 2 – Backend Data Aggregation

- `news_scraper.py`: scrapes headlines via MCP + summarizes
- `reddit_scraper.py`: gathers discussions + sentiment analysis
- `utils.py`: combines content into broadcast format
- Generates TTS audio with ElevenLabs or fallback to gTTS

### Phase 3 – Audio Delivery

- Streamlit receives and plays audio
- Option to download `.mp3` file
  ![Screenshot 2025-06-17 233235](https://github.com/user-attachments/assets/2e204b48-e969-4616-a703-e7fd389bb5bb)




## ⚙️ Setup Guide (Quick Start)

### 🔹 Option 1: Pipenv (Recommended)

```bash
pip install pipenv
pipenv install
pipenv shell
```
🔹 Option 2: pip + virtualenv
```bash
pip install virtualenv
virtualenv venv

# Activate the environment
# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate

pip install -r requirements.txt
```
🔹 Option 3: Conda

```bash
conda create -n newsninja python=3.13
conda activate newsninja
pip install -r requirements.txt
```
Fill in your API keys inside .env:
```bash

BRIGHTDATA_API_KEY=your_key_here
WEB_UNLOCKER_ZONE=your_zone
ELEVENLABS_API_KEY=your_key_here
ANTHROPIC_API_KEY=your_key_here
```

🚀 Run the Application
📦 Full Pipeline (Frontend + Backend)
Use two terminals:

Terminal 1: Backend

```bash

pipenv run python backend.py
```
Terminal 2: Frontend

```bash

pipenv run streamlit run frontend.py
```
▶️ Run Components Individually
🧩 Frontend Only
```bash

streamlit run frontend.py
```
📰 News Scraper (Standalone)
```bash

pipenv run python news_scraper.py
```
🧵 Reddit Scraper (Standalone)
```bash

pipenv run python reddit_scraper.py
```

🧪 Example Use Case
---
1. Launch the app

2. Enter topic: Artificial Intelligence

3. Select data source: Both

4. Click 🚀 Generate Summary

✅ The app will:
---

🔍 Scrape Google News + Reddit

🧠 Summarize content using Anthropic or Ollama

🎙️ Generate and stream an audio report

📘 What is MCP?
---
Model Context Protocol (MCP) is an open standard that allows LLMs to securely interact with external tools and data (e.g., scrapers, APIs).

In this project, MCP helps with:

Scraping dynamic websites

Emulating browsers to bypass anti-bot tools

Allowing the AI to “act” and retrieve real-world content


📚 References with Links
---
BrightData MCP (Mobile Carrier Proxy / Data Platform)

🔗 https://brightdata.com

LangChain (Framework for building LLM applications)

🔗 https://www.langchain.com



Anthropic Claude (AI Assistant by Anthropic)

🔗 https://www.anthropic.com/index/claude

Ollama (Run large language models locally)

🔗 https://ollama.com

ElevenLabs (AI Voice Generation & Text-to-Speech)

🔗 https://www.elevenlabs.io

Streamlit (Framework to create data web apps in Python)

🔗 https://streamlit.io



📄 License
---
MIT License – feel free to use, modify, and distribute with credit.
