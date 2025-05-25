# Task2

# Multi-Tool Conversational AI with LangGraph and Google Gemini
-- This notebook builds a chatbot that can solve math problems, check the weather, and share fashion trends based on location. It uses Google’s Gemini model through LangChain for smart responses and spaCy for understanding locations. LangGraph manages the conversation flow to decide which tool to call.

## How the Notebook is Structured

1. # Setup and API Key Handling
We start by importing required libraries and setting your Google API key securely with getpass. This keeps your key safe while the notebook runs.

2. # Initialize the Language Model
Next, we create a Google Gemini chat model instance (gemini-1.5-flash) with a moderate temperature for balanced replies.

3. # Calculator Tool
We define a simple calculator tool that evaluates basic math expressions. If the input isn’t a clear math expression, it passes it to the language model to respond naturally.

4. # Basic Chatbot Logic with LangGraph
We write a chatbot function that checks your input:

If it contains math operators, it uses the calculator tool.

Otherwise, it sends the input to the language model.
This logic is wrapped in a LangGraph StateGraph with a single node handling the chat.

5. # Visualizing the Chatbot Graph
The notebook then generates and displays a flowchart (using Mermaid format) showing the chatbot’s simple graph structure.

6. # Fashion Tool
We add a new tool to detect locations using spaCy’s named entity recognition. When it finds a city or country, it asks the language model for current fashion trends there. If no location is found, it prompts the user to specify one.

7. # Weather Tool
This tool also uses spaCy to find city names in your input, then calls the OpenWeatherMap API to get current weather details like temperature, humidity, wind, and sunrise/sunset times.

8. # Improved Chatbot Node with Multiple Tools
We upgrade the chatbot function so it:
Uses the calculator for math expressions,
Calls the weather tool if the input mentions weather-related words,
Uses the fashion tool if the input relates to clothing or trends,
Otherwise, asks the user to keep to one topic at a time.
API keys for weather are requested securely when needed.

9. # Conversation Loop
Finally, there’s an interactive loop that:
Prompts you for input,
Sends your input through the chatbot graph,
Prints the bot’s response,
Keeps a running memory of the chat,
Ends when you type exit.

