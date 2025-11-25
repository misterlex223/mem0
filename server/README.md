# Mem0 REST API Server

Mem0 provides a REST API server (written using FastAPI). Users can perform all operations through REST endpoints. The API also includes OpenAPI documentation, accessible at `/docs` when the server is running.

## Features

- **Create memories:** Create memories based on messages for a user, agent, or run.
- **Retrieve memories:** Get all memories for a given user, agent, or run.
- **Search memories:** Search stored memories based on a query.
- **Update memories:** Update an existing memory.
- **Delete memories:** Delete a specific memory or all memories for a user, agent, or run.
- **Reset memories:** Reset all memories for a user, agent, or run.
- **OpenAPI Documentation:** Accessible via `/docs` endpoint.

## Configuration

The server can be configured using environment variables. Create a `.env` file based on the `.env.example` template.

### LLM Configuration
- `LLM_PROVIDER`: LLM provider (default: `openai`, options: `openai`, `anthropic`, `groq`, `ollama`)
- `AI_API_KEY`: API key for OpenAI (required if using OpenAI)
- `OPENAI_MODEL`: Model to use when LLM provider is OpenAI (default: `gpt-4.1-nano-2025-04-14`)
- `ANTHROPIC_MODEL`: Model to use when LLM provider is Anthropic (default: `claude-3-sonnet-20240229`)
- `GROQ_MODEL`: Model to use when LLM provider is Groq (default: `llama3-70b-8192`)
- `OLLAMA_MODEL`: Model to use when LLM provider is Ollama (default: `llama3.1`)
- `LLM_TEMPERATURE`: Temperature setting for LLM (default: `0.2`)
- `LLM_BASE_URL`: Base URL for LLM API (optional, for custom endpoints)
- `OLLAMA_BASE_URL`: Base URL for Ollama server (default: `http://localhost:11434`)

### Embedder Configuration
- `EMBEDDER_PROVIDER`: Embedder provider (default: `openai`, options: `openai`, `anthropic`, `ollama`)
- `EMBEDDER_API_KEY`: API key for embedder (defaults to `AI_API_KEY` if not set)
- `EMBEDDER_MODEL`: Model to use for OpenAI embedder (default: `text-embedding-3-small`)
- `OLLAMA_EMBEDDER_MODEL`: Model to use for Ollama embedder (default: `nomic-embed-text`)

### Database Configuration
- `NEO4J_URI`: Neo4j database URI (default: `bolt://localhost:7687`)
- `NEO4J_USERNAME`: Neo4j username (default: `memgraph`)
- `NEO4J_PASSWORD`: Neo4j password (default: `mem0graph`)
- `POSTGRES_HOST`: PostgreSQL host
- `POSTGRES_PORT`: PostgreSQL port
- `POSTGRES_DB`: PostgreSQL database name
- `POSTGRES_USER`: PostgreSQL username
- `POSTGRES_PASSWORD`: PostgreSQL password
- `POSTGRES_COLLECTION_NAME`: PostgreSQL collection name
- `HISTORY_DB_PATH`: Path for history database (default: `/app/history/history.db`)

## Running the server

Follow the instructions in the [docs](https://docs.mem0.ai/open-source/features/rest-api) to run the server.
