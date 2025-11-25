# Graphs & Nodes Documentation

Hierarchical Agent Teams uses a nested graph structure to organize complex research and writing tasks.

## Orchestration Logic

The system is organized into a **Super Team** that delegates work to two specialized sub-teams:
1. **Research Team**: Handles information gathering and verification.
2. **Writing Team**: Handles content creation, formatting, and analysis.

### `graph.py`
Defines the structure of the three state graphs:
- **`build_super_team_graph`**: The top-level supervisor graph.
- **`build_research_team_graph`**: Focuses on search and scraping.
- **`build_writing_team_graph`**: Focuses on document creation and data visualization.

## Agent Nodes (`node.py`)

Nodes define the behavior and brain of each agent in the graph.

### 1. Supervisor Node
The router of the team. It receives the current state, analyzes the conversation history, and decides which worker should act next or if the task is finished.

### 2. Research Team Nodes
- **Search Node**: Uses the Tavily Search API to find relevant information on the web.
- **Web Scraper Node**: Extracts detailed content from specific URLs identified by the Search node.

### 3. Writing Team Nodes
- **Doc Writer**: Specialized in creating, reading, and editing professional documents.
- **Note Taker**: Summarizes research results and creates outlines for the Doc Writer.
- **Chart Generator**: Uses Python code execution to create visual charts from data.

### 4. Integration Nodes
- **Research Team Node**: A wrapper that allows the Super Team to call the Research Sub-graph as a single unit.
- **Writing Team Node**: A wrapper that allows the Super Team to call the Writing Sub-graph as a single unit.
