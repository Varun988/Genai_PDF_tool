## Use Case
This tool is ideal for researchers, students, or professionals who want to extract and query information from PDF documents efficiently.

## Purpose
To extract content from an uploaded PDF file.
To enable users to ask questions and retrieve answers based on the PDF content, along with sources.

# Key Functionalities
## File Upload:

Users can upload a PDF file via the sidebar.
The uploaded file is temporarily saved for processing.

## Content Processing:

The PDF content is loaded and split into smaller, manageable chunks using the PyPDFLoader.
Embeddings are generated for the chunks using the Hugging Face model (sentence-transformers/all-mpnet-base-v2).
The embeddings are stored in a FAISS vector database, which is saved as a pickle file (vector_index.pkl).

## Query Handling:

Users can input questions about the PDF content.
The FAISS vector store is loaded, and a retrieval-based QA chain (RetrievalQAWithSourcesChain) is used to process the query and generate answers.
Answers and corresponding sources are displayed in the app.

## Tech Stack
Streamlit: Provides a web interface for file upload and user interaction.
LangChain: Handles document loading, splitting, embeddings, and question-answering.
FAISS: Efficient storage and retrieval of embeddings.
Hugging Face: Generates embeddings for text chunks.
ChatGroq: LLM backend to answer queries.

# Workflow

## Upload PDF:

User uploads a PDF file.
The file is read, processed, and split into chunks.
## Embeddings:

Text chunks are embedded using a Hugging Face model.
The embeddings are stored in a FAISS vector database for efficient retrieval.
## Query Processing:

## User enters a question.
The FAISS database is used to retrieve relevant content.
The ChatGroq LLM processes the content to generate an answer.

## Output:

Displays the answer and its sources in the app interface.
