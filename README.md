# Building a Retrieval-Augmented Generation (RAG) System for Customer Query Resolution

Welcome to this project, where we dive into the fascinating world of Retrieval-Augmented Generation (RAG) systems! This repository showcases a robust implementation to build a **learner query resolution system** that leverages course subtitles to create an intelligent, context-aware query-answering system. Whether you're a learner, educator, or AI enthusiast, this project offers a practical blueprint for building scalable, efficient RAG pipelines.

## How to use this system

You can just update the file paths to folders including srt files for courses and this system should work. To test it out you can also download a folder with sample course srt files. 


## Project Overview

There are many data source options to build a learner query resolution system - Course PPTs, course videos, past queries and Subtitles. This simple system transforms raw subtitle files (`.srt`) from educational courses into a powerful knowledge base. By integrating cutting-edge tools like **LangChain**, **CrewAI**, **ChromaDB**, and **OpenAI embeddings**, it enables users to ask questions and receive precise, contextually relevant answers drawn from course content. The project is designed with real-world applications in mind, such as supporting self-paced learners in EdTech environments.

### Key Features

- **Persistent Directory for Efficiency**: The system uses a persistent directory with ChromaDB to store vector embeddings, eliminating the need to reprocess data on every run. This makes it fast and resource-efficient, ideal for repeated queries or large datasets.
- **Metadata-Driven Fast Retrieval**: Metadata (e.g., course names) is embedded into the vector database, enabling rapid filtering and retrieval of relevant content. This ensures answers are both accurate and tailored to specific courses.
- **Subtitle Processing**: Subtitles are chunked and embedded using a recursive text splitter, preserving context while optimizing for vector search.
- **Agentic AI**: A custom-built "Learning Support Specialist" agent, powered by CrewAI, delivers concise, learner-friendly responses with a touch of encouragement.
- **Scalable Design**: Built to handle multiple courses, with examples from "Introduction to Deep Learning using PyTorch," "Building Production-Ready RAG Systems using LlamaIndex," and "Introduction to LangChain."

## How It Works

1. **Data Ingestion**: Subtitle files (`.srt`) from course videos are parsed using `pysrt` and combined into a unified text corpus for each course.
2. **Chunking & Embedding**: Text is split into manageable chunks (1000 characters with 200-character overlap) using LangChain’s `RecursiveCharacterTextSplitter`, then embedded with OpenAI’s embedding model for semantic understanding.
3. **Vector Storage**: Embeddings are stored in a ChromaDB vector database with a persistent directory (`./subtitles_db`), ensuring data persists across sessions for quick access.
4. **Query Processing**: When a query is received, the system uses metadata filters (e.g., course name) to narrow the search space, retrieves the top-k relevant chunks via similarity search, and feeds them to an LLM-powered agent.
5. **Response Generation**: The agent crafts concise, accurate answers (<100 words) based on retrieved content, addressing learners by name and adding encouraging remarks.

## Why This Matters

This RAG system is a game-changer for educational platforms. It reduces manual query resolution time, enhances learner experience with instant, accurate responses, and scales effortlessly with growing course catalogs. The use of a persistent directory cuts down on redundant computation, while metadata ensures retrieval is lightning-fast—perfect for real-time applications.

## Example in Action

**Query**: "What is gradient descent?"  
**Course**: "Introduction to Deep Learning using PyTorch"  
**Response**: "Hi [Learner], gradient descent is an optimization technique to minimize a loss function by iteratively adjusting weights and biases. It’s a cornerstone of deep learning, used in neural networks and regression models. Glad to assist! Feel free to reach out anytime."

## Watch the Tutorial

Curious about the implementation? Check out the detailed walkthrough on YouTube:  
[Watch the Video](https://youtu.be/MK27eV2dcHM)

## Future Enhancements

- Experiment with advanced chunking strategies for even better context preservation.
- Add image processing to handle queries with visual content.
- Incorporate past learner discussions into the vector database for richer responses.
- Optimize retrieval with hybrid search techniques.


---

Happy exploring! Contributions, feedback, and stars are welcome. Let’s make learning smarter together! 🚀