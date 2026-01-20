# PropertyLoop Financial Chatbot

A production-ready chatbot designed to provide accurate financial insights based on portfolio holdings and trade data. The system prioritizes data integrity and avoids hallucinations by using a deterministic, rule-based logic engine.

## Setup Instructions

1. **Install Dependencies**
   Use the provided requirements file to set up your environment:
   ```bash
   pip install -r requirements.txt
   ```

2. **Environment Configuration**
   The system uses environment variables for secure API management. Create a file named `.env` in the root directory and add your Groq API key:
   ```text
   GROQ_API_KEY=your_api_key_here
   ```

3. **Launch the Application**
   Open the Jupyter Notebook to interact with the chatbot:
   ```bash
   jupyter notebook propertyloop_chatbot.ipynb
   ```

## Key Features

*   **Zero Hallucinations**: All calculations are performed directly on the CSV data using Pandas. The LLM is only used to format the final result into natural language.
*   **Transparent Logic**: The intent detection is rule-based, ensuring that the chatbot stays within the scope of the provided data.
*   **Secure API Management**: API keys are handled securely via a .env file.
*   **Reliable Fallback**: Any query that cannot be answered directly from the data returns the specific response: "Sorry can not find the answer".

## Implementation Overview

The chatbot follows a strict processing pipeline:
1. **Query Input**: Receives a user question.
2. **Intent & Parameter Extraction**: Identifies the specific data needed.
3. **Deterministic Computation**: Performs aggregations (counts, sums, comparisons) on the source files.
4. **LLM Formatting**: Uses the Groq Llama 3.3 model to present the computed results in a professional, readable format.
