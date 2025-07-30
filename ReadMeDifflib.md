🧠 AI Agent for Real Estate Search (Text-Only – DiffLib-Based Retrieval)
This proof of concept presents an intelligent AI agent for real estate search using semantic similarity via difflib, a lightweight approach that avoids the need for vector embeddings. It provides relevant property recommendations by matching user queries to listing descriptions based on string similarity—ideal for early-stage prototyping or limited-resource environments.

🚀 Architecture Overview
1. Azure Blob Storage
Stores raw property listing data in text-based JSON format.

2. Text Preprocessing
Extracts key fields such as title, description, price, location, bedrooms, and amenities to form structured records in memory.

3. Lightweight Semantic Search using difflib
User queries are compared against stored listing questions or descriptions.

difflib.get_close_matches() finds the top-n most similar records based on fuzzy string matching.

No vectorization or model inference is required.

4. LangChain Tool Agent (Optional)
Uses LangChain’s tool abstraction to call the search_kb function.

Allows integration with OpenAI LLMs (e.g., GPT-4o-mini) for natural language interpretation and response generation.

5. LLM-Powered Personalization
Azure OpenAI GPT-3.5 or GPT-4o-mini customizes responses based on retrieved listings.

Highlights relevant features such as location, amenities, and fit for user intent.

6. Factual Integrity Check
Ensures that generated summaries accurately reflect listing metadata (price, size, room count).

A verify_facts function cross-references structured fields.

