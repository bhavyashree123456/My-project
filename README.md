# Overview of the Bot
The bot is designed to extract financial data from a PDF document (like a Profit and Loss statement) and allow users to ask questions about that data. The bot processes the PDF, extracts relevant information, creates embeddings for the text data, and uses those embeddings to answer user queries.

 # Key Libraries Used
 1. Streamlit:
     Purpose: Streamlit is a Python library used to create web applications for data science and machine learning projects. It allows you to build interactive applications with minimal effort.
    
     Usage: In this bot, Streamlit is used to create the user interface where users can upload a PDF file and input their questions.
     
     2.pdfplumber:
   Purpose: pdfplumber is a library for extracting text, tables, and metadata from PDF files. It provides a simple interface to work with PDF documents.
     
   Usage: This library is used to read the PDF file and extract the text data, which is then processed into a structured format (like a pandas DataFrame).
     
   3.pandas:
     Purpose: pandas is a powerful data manipulation and analysis library for Python. It provides data structures like DataFrames that make it easy to work with structured data.
     
  Usage: After extracting data from the PDF, pandas is used to organize that data into a DataFrame, which allows for easy querying and manipulation.
  
   4.Sentence Transformers:
     
   Purpose: Sentence Transformers is a library that provides pre-trained models for generating sentence embeddings. These embeddings are vector representations of sentences that capture their semantic meaning.
   
   Usage: The bot uses Sentence Transformers to convert the extracted text data and user queries into embeddings, which can then be compared to find relevant answers.
     
 5.FAISS (Facebook AI Similarity Search):

   Purpose: FAISS is a library for efficient similarity search and clustering of dense vectors. It is particularly useful for large datasets.
   
   Usage: FAISS is used to create an index of the embeddings generated from the extracted data, allowing for fast retrieval of the most relevant information based on user queries.
   
# Workflow of the Bot

User Interface:

The user uploads a PDF file containing financial data using the Streamlit interface.
Data Extraction:

The bot uses pdfplumber to extract text from the PDF. It processes the text to identify relevant financial data and organizes it into a pandas DataFrame.
Data Preparation:

The DataFrame is cleaned and prepared for querying. This may involve handling missing values and ensuring the data is in the correct format.
Embedding Creation:

The bot generates embeddings for the text data in the DataFrame using Sentence Transformers. These embeddings represent the semantic meaning of the text.
Indexing:

The embeddings are indexed using FAISS, allowing for efficient similarity searches.
User Query:

The user inputs a question about the financial data. The bot generates an embedding for the question and uses FAISS to find the most relevant data from the indexed embeddings.
Response Generation:

The bot retrieves the relevant information and displays it to the user through the Streamlit interface.
# Conclusion
This bot combines several powerful libraries to create an interactive application that can extract and query financial data from PDFs. Each library plays a crucial role in the overall functionality, 
from data extraction to user interaction and semantic understanding of the queries. If you have any specific questions about any part of the process or libraries, feel free to ask!

