#LLM
![[CAG Systems 2025-03-21 19.54.29.excalidraw]]
## How It Works – Step by Step

1. ### 🧠 User Query
    
    - User asks a question or issues a command.
    
2. ### 🧭 Context Determination Engine
    
    - Not a retriever, but logic/rules/metadata selectors.
    - E.g., you ask about a specific product, so the system picks that product’s data directly.
    
3. ### 📦 Context Extraction
    
    - Pull the exact info from a structured source:
        - Database
        - GraphQL API
        - JSON
        - Tags, metadata
    - No similarity search, just context targeting.
    
4. ### 📝 Prompt Building
    
    - Combine the structured context with the original query.
    - “Here’s what we know + here’s what the user asked.”
    
5. ### 💬 LLM Generation
    
    - LLM uses the provided context (in prompt) to generate a response.
    
6. ### 📤 Response
    
    - Send it back to the user, possibly with source or context attached.

## 🧠 Example Use Case (CAG)

> **“What is the current status of my order?”**

- System identifies this as an **"order tracking"** intent.
- Looks up the **user’s latest order** from the database.
- Adds order status + tracking info into the prompt.
- LLM formats a nice human-friendly response:
    
    > *“Your order #1234 is currently out for delivery and should arrive by tomorrow.”*
    

No vector search. No guesswork. Clean context.
