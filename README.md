# Telecom RAG Assistant

A Retrieval-Augmented Generation (RAG) application that answers telecom-related questions using information retrieved from a document knowledge base. It combines semantic search with a locally running Large Language Model (LLM) to generate context-aware responses.

## Features

- **Document Retrieval:** Retrieves relevant document chunks using ChromaDB.
- **Semantic Embeddings:** Uses Hugging Face's `sentence-transformers/all-MiniLM-L6-v2` model to convert text into vector embeddings.
- **Vector Search:** Finds relevant information based on semantic similarity.
- **Local LLM:** Uses Ollama with the `qwen3:8b` model to generate responses.
- **Context-Grounded Answers:** Instructs the model to answer using the retrieved context and acknowledge when sufficient information is unavailable.
- **LangChain Integration:** Connects document retrieval, prompt templates, and LLM inference into a RAG chain.

## Tech Stack

- **Python**
- **LangChain**
- **ChromaDB**
- **Hugging Face Sentence Transformers**
- **Ollama**
- **Qwen3 8B**

## How It Works

1. Documents are loaded and divided into smaller chunks.
2. Hugging Face embeddings convert the chunks into numerical vectors.
3. The vectors are stored in ChromaDB.
4. A user's question is used to retrieve the most relevant document chunks.
5. The retrieved chunks are combined into a context string.
6. The context and question are passed to Qwen3 8B through Ollama.
7. The model generates an answer based on the provided context.

## Prerequisites

- Python
- [uv](https://docs.astral.sh/uv/)
- [Ollama](https://ollama.com/)
- Git

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/OmJangam1513/Telecom_RAG_Assistant
cd Telecom_RAG_Assistance
```

### 2. Install dependencies

If the repository contains `pyproject.toml` and `uv.lock`, run:

```bash
uv sync
```

### 3. Download the Ollama model

```bash
ollama pull qwen3:8b
```

### 4. Start Ollama

Make sure the Ollama service is running. You can test the model directly using:

```bash
ollama run qwen3:8b
```

Enter a question to test it, then type `/bye` to exit.

## Running the Project

Run the Python script using:

```bash
uv run python RAG.ipynb.
```

The project is implemented as a Jupyter Notebook, open the notebook in Jupyter and execute its cells in order after installing the dependencies and starting Ollama.

## Example Usage

Ask a question related to the information contained in your telecom documents.

The application retrieves relevant chunks from ChromaDB and passes them to Qwen3 8B to generate a context-aware answer.

**Note:** The quality of the answer depends on the documents available in the knowledge base and the relevance of the retrieved chunks.

## Project Structure

The exact structure depends on your repository files. A typical layout could be:

```text
Telecom_RAG_Assistance/
├── data/                 # Source telecom documents
├── notebooks/            # Jupyter notebooks, if used
├── pyproject.toml        # Project dependencies and configuration
├── uv.lock               # Locked dependency versions
└── README.md             # Project documentation
```

## Future Improvements

- Add support for more document formats.
- Build a web interface for interactive question answering.
- Display retrieved source documents alongside answers.
- Add document upload and indexing functionality.
- Improve retrieval using metadata filtering and reranking.
- Add evaluation metrics for retrieval quality and answer accuracy.

## License

Choose and add an appropriate open-source license if you intend to distribute this project publicly.
