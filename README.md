# 🧠 AI Agent for Real Estate Search (Text-Only RAG)

This proof of concept presents an intelligent AI agent for real estate search, designed using **Retrieval Augmented Generation (RAG)** and Azure services. It delivers **personalized property recommendations** by leveraging text embeddings and language models—without any image analysis.

---

## 🚀 Architecture Overview

### 1. **Azure Blob Storage**
Stores raw property listing data in text-based JSON or document format.

### 2. **Text Preprocessing**
Extracts fields such as `title`, `description`, `price`, `location`, `bedrooms`, and `amenities` to form structured inputs.

### 3. **Text Embeddings via Azure OpenAI**
- Embedding model: `text-embedding-3-small`
- Converts listing descriptions and user queries into dense vector representations.

### 4. **Vector Search with Azure AI Search**
- Embeddings and metadata are indexed in Azure AI Search.
- Supports semantic similarity queries using hybrid search (text + vector).

### 5. **LangChain Agent**
- Receives buyer queries.
- Embeds the input and queries Azure AI Search.
- Retrieves top-k relevant listings.

### 6. **LLM-Powered Personalization**
- Uses GPT-3.5 or GPT-4o-mini via Azure OpenAI to personalize listing descriptions.
- Enhances results based on user intent and highlights relevant features.

### 7. **Factual Integrity Check**
- Verifies that AI-generated descriptions match key details (price, size, rooms).
- Uses a `verify_facts` function to ensure reliability.

---

## 🔍 Example Query

> "Looking for a 2-bedroom modern apartment near Gothenburg city center with a balcony."

### Example Output (Personalized Response):
> _"Modern 2-bedroom apartment in Gothenburg with spacious balcony and open-concept layout—ideal for city living. Close to local parks and transport."_

---

## ✅ Key Benefits

- 💬 Natural language understanding for intuitive search
- 📊 Factual output with integrity checks
- ☁️ Serverless and scalable using Azure services
- 🔍 Fast semantic search with hybrid ranking

---

## 🛠️ Tools & Stack

- Azure Blob Storage
- Azure OpenAI (Embeddings + GPT-4o-mini)
- Azure AI Search (Vector + Metadata)
- LangChain (Chain orchestration)
- Optional: Azure Functions / API Layer

---

## 📁 Future Extensions

- Add structured user profile memory (LangChain memory)
- Include filters (price range, location radius)
- Connect to real-time property APIs

---

> This proof of concept demonstrates how a fully cloud-native, text-based RAG agent can deliver meaningful and reliable results in the real estate domain—without requiring multimodal inputs like images.

