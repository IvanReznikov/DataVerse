# Langchain Basics Onepager

Latest version: 1.1.1

Date of update: 12.11.2023

![Pandas Basics Onepager](https://github.com/IvanReznikov/DataVerse/blob/main/Onepagers/images/langchain_onepager.png?raw=true)

Links:
- [PDF](https://github.com/IvanReznikov/DataVerse/blob/main/Onepagers/pdfs/langchain.pdf)

Topics covered:
- Model Initialization: The code includes initializing OpenAI's language models (text-davinci-003, gpt-3.5-turbo) using langchain.llms.
- Conversation Schemas: It demonstrates managing conversation histories and system instructions through langchain.chat_models and langchain.schema.
- Embeddings: Generating embeddings for queries, specifically for "Birthday gifts for data scientists".
- Prompts: Creating and formatting prompts for different use cases like SEO descriptions and email classification using langchain.prompts.
- Document Handling: Loading documents from various sources (e.g., Wikipedia) and splitting them into manageable texts.
- Retrieval and Vector Storage: Using FAISS for embedding texts and performing similarity searches.
- Memory Management: Implementing conversation buffer memory to manage chat histories.
- Chain Operations: Creating chains for summarizing customer feedback, drafting business email responses, and running predefined chains like summarization and question-answering.
- Agents and Tools: Initializing agents with custom tools and demonstrating the application of these tools in real scenarios, such as unit conversions and text processing.