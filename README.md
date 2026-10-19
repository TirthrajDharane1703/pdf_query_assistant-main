# PDF Query Assistant

Ask questions about a PDF in plain English and get answers grounded in the document itself. Upload a PDF, and the app retrieves the relevant passages and generates an answer rather than making you search or skim manually.

## How it works

1. The PDF is parsed and split into chunks.
2. Each chunk is embedded and indexed in Pinecone for semantic search.
3. When you ask a question, LangChain retrieves the most relevant chunks.
4. The OpenAI API generates an answer grounded in those chunks.
5. Streamlit provides the web interface.

## Tech stack

Python · Streamlit · LangChain · OpenAI API · Pinecone · HTML/CSS

## Setup

```bash
git clone https://github.com/TirthrajDharane1703/pdf_query_assistant-main.git
cd pdf_query_assistant-main
pip install -r requirements.txt
```

Create a `.env` file in the project root (this file is git-ignored and never committed):

```
OPENAI_API_KEY=your_openai_key_here
```

Create a Pinecone index with 1536 dimensions (matching OpenAI's embedding size), and add your Pinecone API key and index name where the app expects them.

Run the app:

```bash
streamlit run main.py
```

## Notes

This was built as a learning project to understand retrieval-augmented generation (RAG) pipelines end to end: chunking, embedding, vector search, and grounded generation.

## License

MIT
