# DocuMind: The Intelligent PDF Assistant

Final project for the Building AI course

## Summary
DocuMind is an AI-powered document assistant that allows users to upload PDF files and ask questions about their content in plain English. Using Retrieval-Augmented Generation (RAG), it extracts specific information from long documents to provide accurate, context-aware answers instantly in about 250 characters.

## Background
In an era of information overload, people spend hours scanning long manuals, legal contracts, or academic papers to find specific details. 

* **Efficiency:** Traditional "Ctrl+F" search only finds exact keywords, not concepts or summaries.
* **Accessibility:** Complex documents are often difficult for non-experts to parse without help.
* **Frequency:** Students, researchers, and office workers face this "needle-in-a-haystack" problem daily.

My personal motivation is to bridge the gap between static data and active conversation, making specialized knowledge accessible to everyone instantly.

## How is it used?
The solution is used through a simple web-based interface. A user uploads a file (e.g., a 50-page insurance policy) and types a question like, "Does this plan cover dental emergencies?" 

1. **Upload:** User provides a PDF.
2. **Analysis:** The AI "reads," chunks, and indexes the document.
3. **Chat:** User asks questions and receives answers based strictly on the document's facts.

<img src="https://raw.githubusercontent.com/3mila26/my_elements_of_ai_project/main/the_tech_stackjpg.jpg" width="600" alt="Project Logic">

```python
import streamlit as st
from langchain.document_loaders import PyPDFLoader

def main():
    st.title("DocuMind Assistant")
    uploaded_file = st.file_uploader("Upload your document", type="pdf")
    if uploaded_file:
        # Load and split the PDF into readable chunks
        loader = PyPDFLoader(uploaded_file)
        pages = loader.load_and_split()
        st.success(f"Analyzed {len(pages)} pages. Ask your question!")

if __name__ == "__main__":
    main()

```

Data sources and AI methodsThe project utilizes user-provided PDF files as the primary data source.
AI might occasionally invent information if the answer isn't clearly in the PDF.Privacy: 
Uploading sensitive documents to cloud-based APIs requires strict data handling considerations.
Formatting: PDFs with complex tables are still difficult for standard AI loaders to read.

What next?
The project could expand to support multi-document analysis. 
To move forward, I would need to implement:
Better OCR for scanned images.Local-first processing to ensure 100% user privacy.

Acknowledgments
Inspired by the Building AI course by Reaktor and University of Helsinki.UI components powered by Streamlit.
