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
