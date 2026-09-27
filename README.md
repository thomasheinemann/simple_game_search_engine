# UdaPlay - AI Game Research Agent Project

## Project Overview
UdaPlay is an AI-powered research agent for the video game industry. This project is provided and guided by udacity inc.
The initial commit marks the template provided by udacity.
The project is divided into two main parts that will help building a sophisticated AI agent capable of answering questions about video games using both local knowledge and web searches.

## Project Structure

### Part 1: Offline RAG (Retrieval-Augmented Generation)
In this part, a Vector Database is using ChromaDB to store and retrieve video game information efficiently.

Key Implementations:
- ChromaDB as a persistent client
- a collection with appropriate embedding functions
- processing and indexing game data from JSON files
- Each game document contains:
  - Name
  - Platform
  - Genre
  - Publisher
  - Description
  - Year of Release

### Part 2: AI Agent Development
Here an intelligent agent that combines local knowledge with web search capabilities is implemented.

The agent has the following capabilities:
1. Answer questions using internal knowledge (RAG)
2. Search the web when needed
3. Maintain conversation state
4. Return structured outputs
5. Store useful information for future use

Implemented tools:
1. `retrieve_game`: Search the vector database for game information.
2. `evaluate_retrieval`: Assess the quality of retrieved results.
3. `game_web_search`: Perform web searches for additional information.
4. `memory_register_tool`: Store a user preference or important fact in long-term memory.
5. `memory_search_tool`: Search long-term memory for previously stored user preferences or facts.

### Directory Structure
```
project/
├── starter/
│   ├── games/           # JSON files with game data
│   ├── lib/             # Custom library implementations
│   │   ├── llm.py       # LLM abstractions
│   │   ├── messages.py  # Message handling
│   │   ├── ...
│   │   └── tooling.py   # Tool implementations
│   ├── Udaplay_01_starter_project.ipynb  # Part 1 implementation
│   └── Udaplay_02_starter_project.ipynb  # Part 2 implementation
```


### Conda Environment
Create a virtual environment using `conda env create -f environment.yml`; and activate it with `conda activate env_simple_game_search_engine`

### Environmental Variable Setup
Create a `.env` file with the following API keys:
```
OPENAI_API_KEY="YOUR_KEY"
TAVILY_API_KEY="YOUR_KEY"
```


## Testing Implementation

The agent is tested with following questions:
- "In which year was 'Super Mario 64' released?"
- "In which year was 'Super Mario 64' released? And did I like it?"
- "In which year was 'Super Mario 64' released? And did I like it? And in which country was it released?"
for the given fact "'Super Mario 64' was often played by me and I enjoyed it.".
