# Ollama-PrivateGPT-Sync 🔒🤖

Ollama-PrivateGPT-Sync is a fully offline, privacy-first implementation of [PrivateGPT](https://github.com/zylon-ai/private-gpt). It allows you to chat with your local documents using advanced Large Language Models (LLMs) without any data leaving your machine.

By leveraging **Ollama**, this version provides a seamless and high-performance backend for local AI inference, bypassing the need for complex C++ compilers or external API keys.

## 🚀 Key Features
- **100% Private**: No data is sent to the cloud. Everything stays on your local hardware.
- **Ollama Integration**: Easy model management and high-performance local inference.
- **Document Intelligence**: Chat with PDFs, Word docs, text files, and more.
- **No Internet Required**: Works perfectly in air-gapped or restricted environments.
- **Zero API Costs**: Run unlimited queries for free on your own machine.

## 🛠️ Tech Stack
- **AI Backend**: [Ollama](https://ollama.com/)
- **LLM**: Llama 3.1 / TinyLlama / Phi-3
- **Framework**: [PrivateGPT](https://github.com/zylon-ai/private-gpt) / [LlamaIndex](https://www.llamaindex.ai/)
- **Vector Store**: [Qdrant](https://qdrant.tech/)
- **Environment**: [Python 3.11](https://www.python.org/) & [Poetry](https://python-poetry.org/)
- **UI**: [Gradio](https://www.gradio.app/)

## 📦 Installation & Setup

1. **Install Ollama**
   Download and install Ollama from [ollama.com](https://ollama.com/).

2. **Clone this repository**
   ```bash
   git clone https://github.com/Aditya-9131/Ollama-PrivateGPT-Sync.git
   cd Ollama-PrivateGPT-Sync
   ```

3. **Install Dependencies**
   ```bash
   python -m poetry install --extras "ui llms-ollama embeddings-ollama vector-stores-qdrant"
   ```

4. **Pull the Required Models**
   ```bash
   ollama pull tinyllama
   ollama pull nomic-embed-text
   ```

5. **Run the Server**
   ```bash
   $env:PGPT_PROFILES='ollama'; python -m poetry run python -m private_gpt
   ```

## ⚙️ Configuration
The project is configured via `settings-ollama.yaml`. You can switch models (e.g., from `tinyllama` to `llama3.1`) by editing the `llm_model` field.

## 🛡️ License
Distributed under the Apache 2.0 License. See `LICENSE` for more information.

---
Created by [Aditya-9131](https://github.com/Aditya-9131)
