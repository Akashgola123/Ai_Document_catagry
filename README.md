# PDF Processor Chatbot

This repository contains a Streamlit application that processes PDF documents by extracting text, performing OCR on images, cleaning text, and handling various NLP tasks using a chatbot interface. The chatbot can extract information, classify documents, translate text, answer questions, and more.

## Setup Instructions

### Requirements

Make sure you have the following installed:
- Python 3.7 or higher
- pip (Python package installer)

### Install Dependencies

Run the following commands to install the necessary Python packages and system dependencies:

```sh
pip install streamlit PyPDF2 easyocr pdf2image
pip install -U "transformers==4.40.0" --upgrade
pip install accelerate bitsandbytes
apt-get install poppler-utils
```

## Directory Setup
Create a directory to store the images extracted from PDF files:
```sh
mkdir text_image_dir
```

## Run the Application
Save the provided Python script as app.py and run the following command to start the Streamlit application:
```sh
streamlit run app.py
```
And also you can Streamlit on Google Colab using LocalTunnel 
If you need to expose the application to the internet (for example, to test it from a different device), you can use LocalTunnel:

```sh
npx localtunnel --port 8501
```

## Usage
Upload a PDF: Use the file uploader in the Streamlit interface to upload a PDF file.
Select Target Language: Choose the target language for translation from the dropdown menu.
Enter Queries: Enter your question, specific extraction request, and review extraction request in the respective text input fields.
Process Document: The application will process the document, performing OCR if needed, cleaning the text, and executing the selected NLP tasks.
View Results: The results will be displayed in the Streamlit interface.

## Design Choices and Technologies
### Libraries and Tools
Streamlit: Provides an interactive web interface for uploading PDFs and displaying results.
PyPDF2: Used to extract text from PDF files.
easyocr: Performs OCR on images to extract text from PDFs with no selectable text.
pdf2image: Converts PDF pages to images for OCR processing.
transformers: Utilizes Hugging Face's Transformers library to handle NLP tasks with pre-trained models.
spaCy: Cleans and lemmatizes extracted text.
LocalTunnel: Exposes the application to the internet for remote access.

## Processing Workflow
1. PDF Extraction: The application first attempts to extract text directly from the PDF. If no text is found, it converts the PDF pages to images and performs OCR.
2. Text Cleaning: Extracted text is cleaned using spaCy to remove stop words, punctuation, and perform lemmatization.
3. NLP Tasks: The cleaned text is processed through various NLP tasks using a pre-trained model (unsloth/llama-3-8b-Instruct-bnb-4bit). Tasks include information extraction, document classification, translation, question answering, specific extraction, and review extraction.

## Chatbot Functionality
The chatbot interface is implemented using predefined prompts for each task. These prompts guide the model in generating appropriate responses based on the uploaded document and user inputs. The flexibility of the design allows easy addition of new tasks and customization of prompts.

## Notes
1. Ensure that the text_image_dir directory exists and is writable.
2. Depending on the size and complexity of the PDF, the processing time may vary.
3. The application currently supports multiple languages for translation, and the target language can be selected from the dropdown menu.
