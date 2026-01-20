# Video Demo Script (90 Seconds)

**0:00 - 0:15 | Introduction**
"Hi, I’m presenting the PropertyLoop Financial Chatbot. The primary goal of this project was to build a system that provides accurate financial insights while strictly avoiding the common issue of AI hallucinations."

**0:15 - 0:35 | Architecture & Hallucination Prevention**
"My solution solves this by separating data computation from language generation. Instead of asking an LLM to find answers in a text block, I use Pandas to perform deterministic calculations directly on the source CSV files. The LLM is only used at the very end—to format our pre-computed numbers into a conversational response."

**0:35 - 0:50 | Setup & Security**
"For the setup, I've prioritized security. API keys are managed through a .env file to ensure no sensitive credentials are hardcoded. The environment is easily manageable with the provided requirements file and setup script."

**0:50 - 1:15 | Demo: Valid Queries**
"Looking at the notebook, the workflow is transparent. We normalize the data, detect the user's intent using a rule-based system, and then execute the math. 
For example, asking 'How many holdings does Garfield have?' returns a precise count from the holdings file. Asking 'Which fund performed better?' triggers a real-time P&L comparison across all funds."

**1:15 - 1:30 | Demo: Fallback & Conclusion**
"If a user asks something out of scope—like a market prediction or the weather—the system returns the exact required fallback: 'Sorry can not find the answer.' 
This architecture ensures the chatbot is reliable, safe, and ready for production use. Thanks for watching."
