# Chatbot Application

A simple conversational chatbot built with LangGraph, LangChain, and Streamlit.

## Overview

This application implements a basic chatbot that maintains conversation history and provides real-time chat interactions through a web interface.

## Architecture

### Backend (`backend.py`)

The backend is built using LangGraph and LangChain:

- **State Management**: Uses `ChatState` TypedDict to manage conversation messages
- **Chat Node**: Processes user messages and generates AI responses using GPT-4o-mini
- **Graph Structure**: Simple linear workflow: START → chat_node → END
- **Checkpointing**: Uses `InMemorySaver` for conversation persistence

#### Key Components:
- `ChatState`: TypedDict with annotated messages list
- `chat_node()`: Processes messages and returns AI responses
- `StateGraph`: Orchestrates the conversation flow
- `checkpointer`: Maintains conversation state across sessions

### Frontend (`frontend.py`)

The frontend is built with Streamlit:

- **Session State**: Maintains conversation history in `st.session_state`
- **Chat Interface**: Uses Streamlit's chat components for user-friendly interaction
- **Message Display**: Shows both user and assistant messages with appropriate styling
- **Thread Management**: Uses configurable thread IDs for conversation isolation

#### Key Features:
- Real-time chat input/output
- Persistent conversation history
- Thread-based conversation management
- Clean chat UI with role-based message display

## Setup

1. **Environment Setup**:
   ```bash
   pip install langgraph langchain streamlit dotenv
   ```

2. **Environment Variables**:
   Create a `.env` file with your OpenAI API key:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```

3. **Run the Application**:
   ```bash
   streamlit run frontend.py
   ```

## Usage

1. Open the application in your browser
2. Type messages in the chat input
3. View the conversation history and AI responses
4. The application maintains conversation context across sessions

## Dependencies

- `langgraph`: Graph-based workflow orchestration
- `langchain`: LLM integration and message handling
- `streamlit`: Web interface framework
- `python-dotenv`: Environment variable management
- `openai`: GPT model integration

## Configuration

The application uses a simple configuration with:
- Thread ID: `thread-1` (configurable)
- Model: GPT-4o-mini
- Checkpointing: In-memory storage

## File Structure

```
app/
├── backend.py      # LangGraph workflow and chat logic
├── frontend.py     # Streamlit web interface
└── README.md       # This documentation
```

## Features

- ✅ Real-time chat interface
- ✅ Conversation history persistence
- ✅ Thread-based conversation management
- ✅ Clean, modern UI
- ✅ Session state management
- ✅ OpenAI GPT-4o-mini integration 
