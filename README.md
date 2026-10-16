# TCS Annual Report – GenAI Chatbot 🤖

A Generative AI chatbot that answers questions about the TCS Annual Report PDF using **Retrieval-Augmented Generation (RAG)**. Built with Python, LangChain, Hugging Face embeddings, FAISS, OpenAI, and Flask REST API.

## 🚀 Project Overview

This project allows users to ask questions about the TCS Annual Report and receive context-based answers. It retrieves relevant information from the document using vector similarity search and passes the retrieved context to an OpenAI language model to generate responses.

## ✨ Features

- PDF document loading and text extraction
- Text chunking for efficient document retrieval
- Semantic embeddings using Hugging Face
- FAISS vector database for similarity search
- Context-based answers using OpenAI LLM
- Flask REST API for real-time question processing
- Postman support for API testing

## 🛠️ Tech Stack

- **Language:** Python
- **GenAI Framework:** LangChain
- **Embedding Model:** `sentence-transformers/all-mpnet-base-v2`
- **Vector Database:** FAISS
- **LLM:** OpenAI
- **Backend:** Flask REST API
- **API Testing:** Postman
- **Document Processing:** PyPDF

## 🔄 How It Works

1. Load the TCS Annual Report PDF.
2. Extract text and split it into chunks.
3. Convert document chunks into vector embeddings.
4. Store the embeddings in a FAISS vector database.
5. Receive a question through the Flask API.
6. Retrieve relevant document chunks using similarity search.
7. Send the question and retrieved context to the OpenAI model.
8. Return the generated answer as a JSON response.

## 📁 Project Structure

```text
TCS-Annual-Report-Chatbot/
│
├── app.py                 # Flask REST API
├── tcs.pdf                # TCS Annual Report PDF (if included)
├── tcs_doc_index/         # Saved FAISS vector database
├── requirements.txt       # Project dependencies
└── README.md              # Project documentation
```

*Note: The PDF and FAISS index must be available locally for the application to run. Update the structure if your repository uses different filenames.*

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd TCS-Annual-Report-Chatbot
```

### 2. Create a virtual environment

```bash
python -m venv ChatBotEnv
```

Activate it on Windows PowerShell:

```powershell
.\ChatBotEnv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install flask langchain langchain-community langchain-text-splitters langchain-huggingface sentence-transformers pypdf faiss-cpu openai
```

### 4. Configure the OpenAI API key

Set your API key in PowerShell:

```powershell
$env:OPENAI_API_KEY="your_openai_api_key"
```

Keep your API key private. Never upload it to GitHub.

### 5. Run the application

```bash
python app.py
```

The Flask server runs locally at:

```text
http://127.0.0.1:5000
```

## 🧪 Test with Postman

- **Method:** `POST`
- **URL:** `http://127.0.0.1:5000/tcs`
- **Body:** Select `raw` → `JSON`

Example request:

```json
{
  "tcs_question": "How is TCS performing in terms of revenue?"
}
```

Example response format:

```json
{
  "gpt response": "Answer generated using the retrieved annual report context."
}
```

The actual answer depends on the retrieved document content and the language model response.

## 🎯 Learning Outcomes

- Understanding Retrieval-Augmented Generation (RAG)
- Working with embeddings and vector databases
- Implementing semantic document search
- Integrating LLMs with a Python application
- Building and testing REST APIs
- Developing document-based question-answering systems

## 🔮 Future Enhancements

- Support multiple PDF documents
- Add a web-based chatbot interface
- Improve retrieval accuracy with relevance thresholds
- Add source citations for generated answers
- Deploy the application to a cloud platform

## 👩‍💻 Author

**Sravya Mamidi**

B.Tech Computer Science and Engineering | Aspiring GenAI & Software Developer
---

If you find this project useful, consider giving the repository a ⭐.

**Disclaimer:** This is an educational project. Answers depend on the source document, retrieved context, and model output. Verify financial information against the original TCS Annual Report.
