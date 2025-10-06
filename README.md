# Dhruvai
🧠 Dhruva AI — Your Personalized Knowledge-Based Chatbot

Dhruva AI is an intelligent conversational assistant built using Streamlit, LangChain, Groq, and NVIDIA Embeddings. It allows users to upload documents, convert them into vector embeddings, and chat with an AI that retrieves and reasons over those uploaded files.

The system combines retrieval-augmented generation (RAG) with large language models to give context-aware, human-like responses.

🚀 Features

🗂 Upload and manage your documents directly in the app

🔍 Vector store creation and persistence with FAISS

🧬 NVIDIA Embeddings for document understanding

💬 ChatGroq (Gemma2-9b-It) as the LLM for conversational reasoning

⚡ RAG-based responses — grounded in your uploaded data

💾 Option to reuse existing vector databases for faster startup

🖥️ Beautiful Streamlit UI with a sidebar upload panel

🧩 Project Structure
📂 dhruva-ai/
├── 📜 app.py                # Main Streamlit app
├── 📜 .env                  # Environment variables (API keys)
├── 📂 uploaded_docs/        # Uploaded documents folder
├── 📜 vectorstore.pkl       # Saved FAISS vector database
├── 📜 requirements.txt      # Dependencies list
└── 📘 README.md             # Project documentation

⚙️ Installation Guide

Follow these steps to run Dhruva AI locally.

1. Clone this repository
git clone https://github.com/<your-username>/dhruva-ai.git
cd dhruva-ai

2. Create and activate a virtual environment

Windows:

python -m venv venv
venv\Scripts\activate


Mac/Linux:

python3 -m venv venv
source venv/bin/activate

3. Install dependencies
pip install -r requirements.txt


(Create requirements.txt with this content if not present)

streamlit
python-dotenv
langchain
langchain-groq
langchain-nvidia-ai-endpoints
langchain_community
groq
faiss-cpu
pickle5

4. Set up environment variables

Create a .env file in the root folder and add your API keys:

API_KEY=your_groq_api_key_here
NVIDIA_API_KEY=your_nvidia_api_key_here


⚠️ Never commit .env or API keys to GitHub.
Add .env to your .gitignore file to keep it private.

🧠 How It Works

Document Upload
Users can upload files (PDFs, text files, etc.) through the sidebar. Uploaded files are stored in the uploaded_docs/ directory.

Embedding Creation
Documents are split into smaller chunks (512 tokens, with 150-token overlap).
Each chunk is embedded using NVIDIA Embeddings (nvidia/nv-embedqa-e5-v5).

Vector Store Management

Embeddings are stored using FAISS.

Users can reuse or regenerate the vector store (vectorstore.pkl).

Chat with Context
When a user enters a question:

The system retrieves the most relevant chunks from FAISS.

The question and context are sent to Groq’s Gemma2-9b-It model.

The model generates a coherent, grounded answer.

🗨️ Usage

Run the Streamlit app:

streamlit run app.py


Then open your browser at:

http://localhost:8501

Steps:

Upload documents in the sidebar panel.

Choose whether to reuse an existing vector store.

Type your query in the chat box.

Get interactive, context-aware answers from Dhruva AI!

🧰 Tech Stack
Component	Technology
Frontend	Streamlit
LLM	Groq - Gemma2-9b-It
Embeddings	NVIDIA nv-embedqa-e5-v5
Vector Database	FAISS
Framework	LangChain
File Storage	Local (uploaded_docs/)
Persistence	Pickle serialization
🔒 Security Notes

Always keep API keys hidden using .env files or environment variables.

Add the following to your .gitignore file:

.env
vectorstore.pkl
uploaded_docs/


Never expose private keys in code or commit history.

💡 Example Conversation

User: What does the uploaded research paper say about quantum entanglement?
Dhruva AI: Based on the uploaded document, quantum entanglement is described as a non-local correlation between particles, transcending spacetime limits and suggesting a deeper layer of interconnected reality...

📈 Future Enhancements

Support for PDF parsing, images, and multi-format documents

Add cloud-based vector storage (Pinecone, Chroma, or Weaviate)

Fine-tune chat personality and tone

Multi-user session support

Integration with StarVault for decentralized document security

🧑‍💻 Author

Harsh Goyal
📚 4th-year Computer Science Student | Researcher on Theory of Everything | Founder of StarVault
🌐 [Website Concept: Vasudevayekutumbhakam — “The World is One Family”]

🪐 License

This project is open-source under the MIT License.
You are free to use, modify, and distribute it with attribution.
