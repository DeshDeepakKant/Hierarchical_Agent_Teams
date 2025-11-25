# Tools Documentation

The Hierarchical Agent Teams system provides specialized agents with access to a variety of modular tools for research, document management, and data processing.

## Tool Categories

### 1. Web Search & Information Gathering
- **`tavily_tool`**: Uses the Tavily Search API to find high-quality information online. It is optimized for AI agents and returns the most relevant snippets.
- **`scrape_webpages`**: Uses `WebBaseLoader` to load and parse content from specific URLs, providing detailed context for the agents.

### 2. Document & File Management
These tools operate within a dedicated workspace directory managed by the system.
- **`create_outline`**: Saves a structured list of points as an outline file.
- **`read_document`**: Reads text from a specified file, with support for line range selection.
- **`write_document`**: Creates a new text file with provided content.
- **`edit_document`**: Modifies an existing file by inserting text at specific line numbers.

### 3. Data Analysis & Visualization
- **`python_repl_tool`**: Provides a Python execution environment for performing calculations, processing data, and generating visual charts/images using libraries like `matplotlib`.

## Workspace Security
All file operations are restricted to the `WORKING_DIRECTORY` to prevent directory traversal and ensure data is organized within the project's scope.
