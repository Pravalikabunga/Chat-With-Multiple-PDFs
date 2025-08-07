# Overview
This application allows users to upload multiple PDF files and interact with their content using natural language queries. It leverages Google's Gemini AI to provide accurate and contextual responses based on the uploaded documents.

# Features
1. PDF Processing
   - Upload multiple PDF files
   - Extract text content from PDFs
   - Split text into manageable chunks for processing
2. AI-Powered Chat
   - Natural language question answering
   - Context-aware responses
   - Built on Google's Gemini AI model
3. Vector Storage
   - Uses FAISS for efficient similarity search
   - Local storage of processed documents
   - Google's Generative AI embeddings

# Prerequisites
1. Python 3.8 or higher
2. Google API key with access to Gemini AI
3. Required Python packages (listed in requirements.txt)

# Installation
1. Clone the repository:
   git clone https://github.com/Pravalikabunga/Chat-With-Multiple-PDFs.git
   cd Chat-With-Multiple-PDFs
2. Create and activate a virtual environment:
   python -m venv venv
   .\venv\Scripts\activate  # On Windows
3. Install dependencies:
   pip install -r requirements.txt
4. Set up environment variables:
   - Create a .env file in the project root
   - Add your Google API key: GOOGLE_API_KEY=your_google_api_key_here

# Usage
1. Run the application: streamlit run app.py
2. In the web interface:
   - Use the sidebar to upload one or more PDF files
   - Click "Submit & Process" to analyze the documents
   - Enter your question in the main input field
   - View the AI's response below the input field

# File Structure
### app.py
 - Main application file
### requirements.txt
 - Python dependencies
### .env
 - Environment variables (create this file)
### faiss_index/ - Directory for storing document embeddings
- index.faiss - FAISS vector store
- index.pkl - FAISS index metadata

# API Reference
### Main Functions
1. get_pdf_text(pdf_docs)
   - Extracts text from uploaded PDF files
   - Parameters: List of uploaded PDF files
   - Returns: Combined text from all PDFs
2. get_text_chunks(text)
   - Splits text into chunks for processing
   - Parameters: Combined text string
   - Returns: List of text chunks
3. get_vector_store(text_chunks)
   - Creates and saves vector embeddings
   - Parameters: List of text chunks
   - Saves embeddings to local storage
4. get_conversational_chain()
   - Sets up the question-answering chain
   - Returns: Configured QA chain
5. user_input(user_question)
   - Processes user questions and generates responses
   - Parameters: User's question string
   - Displays response in the Streamlit interface

# Error Handling
- The application will indicate if an answer cannot be found in the provided context
- Errors during PDF processing will be displayed in the console
- Missing API keys will raise

# Troubleshooting
1. API Key Issues
   - Ensure your Google API key is valid and has access to the Gemini API
   - Verify the .env file is in the correct location
2. Dependency Issues
   - If you encounter missing modules, run:
      pip install -r requirements.txt
3. Large PDFs
   - Very large PDFs may take time to process
   - Consider splitting extremely large documents

# Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

