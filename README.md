<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

DocuMind: The Intelligent PDF Assistant

Final project for the Building AI course

Summary: DocuMind is an AI-powered document assistant that allows users to upload PDF files and ask questions about their content in plain English. 
Using Retrieval-Augmented Generation (RAG), it extracts specific information from long documents to provide accurate, context-aware answers instantly.

Background: In an era of information overload, people spend hours scanning long manuals, legal contracts, or academic papers to find specific details.
Efficiency: Traditional "Ctrl+F" search only finds exact keywords, not concepts.

Accessibility: Complex documents are often difficult for non-experts to parse.

Frequency: Students, researchers, and office workers face this "needle-in-a-haystack" problem daily.
My personal motivation is to bridge the gap between static data and active conversation, making specialized knowledge accessible to everyone.

How is it used?
The solution is used through a simple web-based interface. 
A user uploads a file (e.g., a 50-page insurance policy) and types a question like, "Does this plan cover dental emergencies?
"Upload: User provides a PDF.Analysis: The AI "reads" and indexes the document chunks.
Chat: User asks questions and receives answers based strictly on the document's facts.
This is ideal for students cramming for exams, lawyers reviewing discovery documents, or homeowners reading appliance manuals.

Python:

import streamlit as st
from langchain.document_loaders import PyPDFLoader
from langchain.vectorstores import Chroma

def process_document(pdf_path):
    # This core logic breaks the PDF into searchable 'chunks'
    loader = PyPDFLoader(pdf_path)
    pages = loader.load_and_split()
    return pages

def main():
    st.title("DocuMind Assistant")
    uploaded_file = st.file_uploader("Upload your document", type="pdf")
    if uploaded_file:
        st.success("Document analyzed. Ask me anything!")
        
Data sources and AI methodsThe project utilizes user-provided PDF files as the primary data source.
NLP Methods: Text chunking and Embedding (converting text to vectors).
AI Model: Uses Large Language Models (LLMs) like GPT-4o-mini via API or Llama 3 via Ollama.
Vector Database: ChromaDB or FAISS for efficient similarity searches.
ComponentTechnologyInterfaceStreamlitAI FrameworkLangChainEmbeddingsOpenAI / HuggingFaceChallengesHallucination: AI might occasionally invent information if the answer isn't clearly in the PDF.
Privacy: Uploading sensitive documents to cloud-based APIs requires strict data handling considerations.
Formatting: PDFs with complex tables or handwritten notes are still difficult for standard AI loaders to read accurately.

What next?
The project could expand to support multi-document analysis, allowing a user to "chat" with an entire library of books at once. 
To move forward, I would need to implement:Better OCR (Optical Character Recognition) for scanned images.Local-first processing to ensure 100% user privacy.
Integration with citation features so the AI can point to the exact page and paragraph it used.
AcknowledgmentsInspired by the LangChain documentationMethodology based on the Building AI course by Reaktor and University of Helsinki.
UI components powered by Streamlit.


![image of charts](/the_tech_stackjpg.jpg)


picture made by AI
