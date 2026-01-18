# my_elements_of_ai_project
Ask My PDF Assistant. This project teaches you how to connect a "brain" (the LLM) to "memory" (your data).

1. The Tech Stack (Beginner Friendly)
Language: Python (The industry standard for AI).

Interface: Streamlit (Turns Python scripts into web apps in minutes).

Orchestration: LangChain (The "glue" that connects the AI to your files).

Brain: OpenAI API (e.g., GPT-4o-mini) or Ollama (if you want to run it for free on your own computer).

2. How it Works (The Logic)
You aren't just sending text to a chatbot. You are building a pipeline:

Ingest: You upload a PDF.

Chunk: The code breaks the PDF into small paragraphs.

Embed: Each paragraph is converted into a list of numbers (vectors) that represent its meaning.

Retrieve: When you ask a question, the app finds the 3 most relevant paragraphs.

Answer: The LLM reads those 3 paragraphs and answers your question based only on that info.

3. Step-by-Step Blueprint
   Step	Task	Why?
1	Install Python & VS Code	Set up your workbench.
2	pip install streamlit langchain pypdf	Get the necessary "lego bricks."
3	Create a basic Streamlit UI	Make a button to upload a file and a text box for questions.
4	Connect the PDF loader	Use PyPDFLoader to let Python "read" the file.
5	Add the "Brain"	Send the text to an AI model to get a response.
