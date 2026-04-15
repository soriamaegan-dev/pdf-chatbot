# 📄 PDF Chatbot — Build a Chatbot for Your Data

An AI-powered chatbot that reads and understands your PDF documents,
allowing you to ask questions and get intelligent answers about the
content using IBM WatsonX Llama 3 and LangChain.


## 📖 About
This project demonstrates how to build a full-stack chatbot that can
comprehend and answer questions related to the content of any PDF
document. Upload your PDF and start asking questions — the chatbot
will analyze the document and provide accurate, context-aware responses.

## 🚀 Features
- 📄 **PDF Upload** — Upload any PDF document
- 🧠 **AI Comprehension** — IBM WatsonX Llama 3 understands your document
- 💬 **Smart Q&A** — Ask questions and get context-aware answers
- 🔍 **Semantic Search** — ChromaDB vector store for efficient retrieval
- 📝 **Chat History** — Maintains conversation context
- 🌐 **Web Interface** — Clean and intuitive chat UI

## 🛠️ Tech Stack
- **LLM**: IBM WatsonX Llama 3 (lab) / HuggingFaceH4/zephyr-7b-beta (HF Spaces)
- **Embeddings**: sentence-transformers/all-MiniLM-L6-v2
- **Vector Store**: ChromaDB
- **Framework**: LangChain, Flask
- **Frontend**: HTML, CSS, JavaScript, Bootstrap, jQuery

## 📂 Project Structure
```
pdf-chatbot/
├── server.py                    # Flask backend server
├── worker.py                    # LangChain AI processing (WatsonX)
├── requirements.txt             # Project dependencies
├── hf-pdf-chatbot/
│   ├── app.py                  # Gradio app for HF Spaces
│   └── requirements.txt        # HF Spaces dependencies
├── static/
│   ├── script.js               # Frontend JavaScript
│   └── style.css               # Frontend styles
└── templates/
    └── index.html              # Chat interface webpage
```

## 💬 How It Works
1. User uploads a PDF file via the web interface
2. Flask backend receives and saves the PDF
3. LangChain loads and splits the PDF into chunks
4. Chunks are embedded and stored in ChromaDB vector store
5. User asks a question in the chat interface
6. LangChain retrieves relevant chunks using semantic search
7. LLM generates an answer based on the chunks
8. Answer is returned and displayed in the chat interface

## ⚙️ API Endpoints
```
GET  /                    # Serves the chat interface
POST /process-message     # Processes user questions
POST /process-document    # Uploads and processes PDF
```

## 🔧 Run in IBM Skills Network Lab
```bash
# Step 1 - Set up virtual environment
pip3 install virtualenv
virtualenv my_env
source my_env/bin/activate

# Step 2 - Clone the repo
git clone https://github.com/soriamaegan-dev/pdf-chatbot
cd pdf-chatbot

# Step 3 - Install dependencies
pip install -r requirements.txt
pip install "langchain==0.2.16" "langchain-core==0.2.38" \
"langchain-community==0.2.16" "langchain-huggingface==0.0.3" \
"langchain-ibm==0.1.12" "pydantic==1.10.13"

# Step 4 - Run the server
python3 server.py
```

Then open port **8000** via Skills Network Toolbox in external browser.

## 🔁 How to Restore After Lab Session Ends
```bash
source /home/project/my_env/bin/activate
cd /home/project/pdf-chatbot
python3 server.py
```

## ⚠️ Important Notes
- IBM WatsonX credentials are provided by IBM Skills Network
- The `project_id="skills-network"` only works inside the IBM lab
- HuggingFace API endpoints are blocked in the IBM lab environment
- The HF Spaces version uses `zephyr-7b-beta` instead of WatsonX
- To run outside the lab you need your own IBM Cloud credentials

## 💾 Why GitHub?
GitHub permanently saves your code so it's never lost when the
lab session ends:

| | Description |
|--|--|
| **GitHub** | 📦 Saves your code permanently |
| **IBM Lab** | 🖥️ Temporary workspace — wiped when session ends |
| **HF Spaces** | 🌐 Runs your code with a permanent public URL |

## 🧠 Models Used
| Model | Where | Purpose |
|-------|-------|---------|
| `meta-llama/llama-3-3-70b-instruct` | IBM Lab | Question answering |
| `HuggingFaceH4/zephyr-7b-beta` | HF Spaces | Question answering |
| `sentence-transformers/all-MiniLM-L6-v2` | Both | Text embeddings |

## 📚 What I Learned
- How to build a RAG (Retrieval Augmented Generation) application
- How to use LangChain for document processing
- How to use ChromaDB as a vector store
- How to integrate IBM WatsonX LLMs
- How to build a Flask web application with file upload
- How to use semantic search for document retrieval
- How to deploy AI apps to Hugging Face Spaces

## 🎓 Built As Part Of
IBM AI Developer Professional Certificate — Coursera
Lab: Build a Chatbot for Your Data
