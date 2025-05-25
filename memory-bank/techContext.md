# Technical Context: Cognee

## Technologies Used

### Programming Languages
- **Python**: Primary development language with async/await support
- **Markdown**: Documentation format
- **TypeScript/JavaScript**: Used in the frontend components

### Core Libraries
- **Pydantic**: Data validation and serialization
- **FastAPI**: API framework for the Cognee server
- **NetworkX**: Graph manipulation and algorithms
- **D3.js**: Graph visualization in the browser
- **asyncio**: Asynchronous I/O handling
- **uvicorn**: ASGI server for serving the API

### Database Technologies
- **Neo4j**: Graph database option for storing knowledge graphs
- **Kuzu**: Alternative graph database option
- **Weaviate**: Vector database for semantic search
- **PostgreSQL**: Relational database with pgvector for vector operations

### LLM Integration
- **OpenAI API**: Default LLM provider with models like GPT-4o-mini
- **Ollama**: Support for local model deployment
- **Gemini**: Alternative LLM provider support
- **HuggingFace**: Integration with open-source models

### Containerization & Deployment
- **Docker**: Container packaging and deployment
- **Docker Compose**: Multi-container orchestration
- **Kubernetes/Helm**: Advanced deployment options

### Frontend
- **Next.js**: Framework for the web UI
- **React**: UI component library
- **Model Context Protocol (MCP)**: Integration with Claude Desktop and similar tools

## Development Setup

### Local Development Environment
```
# Core requirements
- Python 3.8+
- Poetry/pip/uv for dependency management
- Docker (optional for containerized databases)
- OpenAI API key or alternative LLM provider credentials
```

### Configuration
- Environment variables through .env files
- Configuration options for database selection
- LLM provider configuration
- Vector embedding settings

### Testing Infrastructure
- Unit tests for core components
- Integration tests for pipelines
- Evaluation framework for comparing memory performance

## Technical Constraints

### Performance Considerations
- LLM API latency impacts processing time
- Graph database query performance varies by database size
- Memory consumption grows with graph complexity
- Embedding generation can be compute-intensive

### Security Limitations
- API key management for LLM services
- Database credential security
- Access control to memory contents

### Scalability Factors
- Database scaling requirements for large memory graphs
- Processing pipeline throughput
- Concurrent request handling

## Dependencies

### External Services
- LLM providers (OpenAI, Google, etc.)
- Cloud storage (optional for S3-based storage)

### Internal Dependencies
- Graph database must be available for cognify operations
- Vector database must be available for semantic search
- LLM connection must be functional for knowledge extraction

## Tool Usage Patterns

### Environment Setup
```python
import cognee
import asyncio
import os

# Configure environment
os.environ["LLM_API_KEY"] = "your_api_key"
```

### Basic Memory Operations
```python
# Add content to memory
await cognee.add("Natural language processing (NLP) is an interdisciplinary subfield of computer science.")

# Process and build knowledge graph
await cognee.cognify()

# Query the memory
results = await cognee.search("Tell me about NLP")
```

### Advanced Configuration
```python
# Select database provider
cognee.config.set_graph_database_provider("neo4j")
cognee.config.set_vector_db_provider("weaviate")

# Set data directories
cognee.config.data_root_directory("path/to/data")
cognee.config.system_root_directory("path/to/system")
```

### Pipeline Customization
```python
from cognee.modules.pipelines.tasks.task import Task
from cognee.modules.pipelines import cognee_pipeline

# Define custom tasks
custom_tasks = [
    Task(classify_documents),
    Task(extract_chunks_from_documents),
    Task(extract_graph_from_data, graph_model=CustomGraph),
]

# Run custom pipeline
await cognee_pipeline(tasks=custom_tasks, datasets="my_dataset")
```
