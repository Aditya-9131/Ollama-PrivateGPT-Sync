hat # Running PrivateGPT on Windows

To run PrivateGPT, follow these steps in your terminal (PowerShell is recommended).

### 1. Project Prerequisites
Ensure you are in the project root:
`cd c:\Users\adity\Downloads\private-gpt-main\private-gpt-main`

### 2. Environment Setup
I have already installed **Poetry** for you. Now you need to install the project dependencies with the UI and Local LLM (llama-cpp) extras:

```powershell
python -m poetry install --extras "ui llms-llama-cpp vector-stores-qdrant embeddings-huggingface"
```

### 3. Download Models
PrivateGPT requires model files. This command will download several GBs (Llama 3.1 and Nomic Embedding):

```powershell
python -m poetry run python scripts/setup
```

### 4. Running the Project
Once the models are downloaded, you can start the PrivateGPT server with the **local** profile:

```powershell
$env:PGPT_PROFILES='local'; python -m poetry run python -m private_gpt
```

The application will be available at **http://localhost:8001** in your browser.

---

### Alternative: Using Ollama (Highly Recommended)
If you already have [Ollama](https://ollama.com) installed:

1. Pull the models:
   ```powershell
   ollama pull llama3.1
   ollama pull nomic-embed-text
   ```

2. Run PrivateGPT with the **ollama** profile:
   ```powershell
   $env:PGPT_PROFILES='ollama'; python -m poetry run python -m private_gpt
   ```

### Troubleshooting
If `poetry` is not recognized, use `python -m poetry` instead.
If you get memory errors, ensure you have enough RAM for the model (8GB+ recommended).
