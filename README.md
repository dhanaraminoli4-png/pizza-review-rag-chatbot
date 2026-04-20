# pizza-review-rag-chatbot

🍕 Pizza Review QA Chatbot (LangChain + Ollama)

This project is a Retrieval-Augmented Generation (RAG) chatbot that answers questions about a pizza restaurant using real customer reviews.

-------------------------------------------------------------------------------------------------------------------------------------------
It uses:

LangChain for chaining prompts and models
Ollama for running local LLMs and embeddings
ChromaDB as a vector database
Pandas for handling review data
🚀 Features
Ask natural questions like:
“How are the vegan options?”
“Is the pizza worth the price?”
Retrieves relevant reviews from a dataset
Uses an LLM to generate human-like answers
Runs locally (no API keys required)

---------------------------------------------------------------------------------------------------------------------------------------------
📁 Project Structure
.
├── main.py                # Chat loop + LLM interaction
├── vector.py              # Vector DB setup and retriever
├── realistic_restaurant_reviews.csv   # Dataset
├── chrome_langchain_db/   # Persistent Chroma DB
├── README.md

---------------------------------------------------------------------------------------------------------------------------------------------

⚙️ Setup Instructions
1. Clone the repository
git clone https://github.com/your-username/pizza-rag-chatbot.git
cd pizza-rag-chatbot
2. Create a virtual environment
python -m venv venv

Activate the VM:
Windows
venv\Scripts\activate
Mac/Linux
source venv/bin/activate
3. Install dependencies
pip install langchain langchain-core langchain-chroma langchain-ollama pandas
4. Install and run Ollama

Download Ollama and run:
ollama pull llama3.2
ollama pull mxbai-embed-large
▶️ Running the Project
python main.py

You’ll see:
Ask your question (q to quit):

Example:
how are the vegan options

---------------------------------------------------------------------------------------------------------------------------------------------

🧠 How It Works
Step 1: Data Processing
Reviews are loaded from a CSV file
Each review is converted into a Document

Step 2: Embeddings
Uses mxbai-embed-large to convert text into vectors

Step 3: Vector Storage
Stored in ChromaDB
Persisted locally (./chrome_langchain_db)

Step 4: Retrieval
Top 5 relevant reviews are fetched using similarity search

Step 5: Generation
llama3.2 generates answers using:
User question
Retrieved reviews

---------------------------------------------------------------------------------------------------------------------------------------------

💬 Prompt Template
You are an expert in answering questions about a pizza restaurant

Here are some relevant reviews: {reviews}
Here is the question to answer: {question}

---------------------------------------------------------------------------------------------------------------------------------------------

🧪 Example Output
Question:
How are the vegan options?

Answer:
Mixed reviews
Some customers loved vegan cheese and toppings
Others disliked texture and taste
Overall: improving but inconsistent

---------------------------------------------------------------------------------------------------------------------------------------------

🛠️ Tech Stack
Python
LangChain
Ollama (LLMs + embeddings)
ChromaDB
Pandas
