# **MedBot - RAG-based Chatbot Application**

MedBot is a **Retrieval-Augmented Generation (RAG)**-based chatbot application that answers user queries based on a custom knowledge base. It utilizes preloaded data stored in a **vector database (FAISS)** and provides accurate responses along with source citations. If a user asks something outside the scope of the available data, MedBot politely informs the user that it lacks sufficient knowledge.

---

##  **Features**

- Load PDF documents to extract knowledge.  
- Split text into smaller chunks for effective vector search.  
- Create and store vector embeddings using **FAISS**.  
- Query the vector database to find relevant information.  
- Generate responses based on stored knowledge and cite sources.  
- Handles out-of-scope questions gracefully.

---

## **Tech Stack**

- **Python** - Core language for backend logic.
- **LangChain** - Framework to build context-aware LLM applications.
- **FAISS (Facebook AI Similarity Search)** - Vector store to perform similarity search on text chunks.
- **Hugging Face Sentence Transformers** - To generate high-quality embeddings.
- **Streamlit** - Frontend to create a user-friendly interface.

---

## **How It Works**

### 1. **Load PDF Documents**
- Documents are loaded from the `data/` directory using `PyPDFLoader` from LangChain.
- Extracted text is split into smaller chunks using `RecursiveCharacterTextSplitter`.

### 2. **Generate and Store Embeddings**
- The text chunks are converted into embeddings using `HuggingFaceEmbeddings`.
- FAISS stores the embeddings locally in the `vectorstore/db_faiss/` directory.

### 3. **User Query and Retrieval**
- When a user enters a query, MedBot searches for similar text chunks using FAISS.
- If relevant information is found, it answers the query and provides source citations.
- If no relevant data is found, MedBot returns: I'm sorry, I don't have enough knowledge about that.


---

## **Installation and Setup**

### 1. **Clone the Repository**
```bash
git clone https://github.com/your-username/medbot.git
cd medbot
```
### 2. **Create a Virtual Environment**
```bash
# For Windows
python -m venv env
# For Mac/Linux
python3 -m venv env
```
### 3. **Activate the Virtual Environment**
```bash
# On Windows
env\Scripts\activate
# On Mac/Linux
source env/bin/activate
```

### 4. **Install Required Packages**
```bash
pip install -r requirements.txt
```

### 5.  **Run the Application**
```bash
streamlit run main.py
```


