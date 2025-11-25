# Backend Documentation

The backend of Hierarchical Agent Teams is built with **FastAPI** and **LangGraph**, providing a robust system for multi-agent coordination and real-time communication.

## Key Components

### 1. `main.py`
The entry point of the application. It handles:
- **FastAPI server initialization**.
- **WebSocket Streaming**: Under the `/ws/stream` endpoint, it manages real-time interaction between users and agents. It uses an `AsyncYieldCollector` to capture and stream agent outputs.
- **File Management**: Endpoints for listing (`/files`) and downloading (`/download`) generated documents.
- **Environment Setup**: Loads configuration from `.env`, including the OpenAI API key.

### 2. `collector.py`
Implements `AsyncYieldCollector`, an asynchronous queue-based system used to collect messages from multiple agents and stream them to the WebSocket.

### 3. Server Management
The backend utilizes **Uvicorn** as the ASGI server. It can be started using:
```bash
python main.py
```
or
```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/ws/stream` | WebSocket | Real-time agent collaboration stream |
| `/files` | GET | List all generated files in the workspace |
| `/download` | GET | Download a specific file by name |

## State Management
The system uses **LangGraph's stateful graphs** to track message history and routing decisions across multiple teams.
