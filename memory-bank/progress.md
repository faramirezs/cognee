# Progress: Cognee

## What Works
- Core API functionality (add, cognify, search)
- Multiple graph database integrations (Neo4j, Kuzu)
- Knowledge graph creation from text content
- Document classification and chunking
- Graph visualization capabilities
- Memory retrieval via semantic search
- Basic integration with LLM providers
- Docker containerization for local deployment
- Model Context Protocol (MCP) integration for Claude Desktop
- Examples for basic usage scenarios
- International documentation (English, Portuguese, Chinese)
- Local Hugging Face embedding models (all-MiniLM-L6-v2)

## What's Left to Build
- Advanced multimedia processing improvements
- More comprehensive evaluation frameworks
- Additional graph database integrations
- Enhanced ontology support and customization
- Improved documentation and tutorials
- Performance optimizations for large-scale deployments
- More extensive frontend capabilities
- Extended API features for advanced use cases
- Additional integration examples with other AI frameworks
- Better embedding model compatibility documentation

## Current Status
- Basic functionality is operational and stable
- Memory bank has been initialized with core documentation
- Project structure and architecture have been documented
- Testing framework is in place but could be expanded
- Example implementations demonstrate key capabilities
- Community contributions are being encouraged through documentation
- Configuration challenges with API proxies have been identified and resolved

## Known Issues
- Performance bottlenecks with very large knowledge graphs
- Dependency management complexity across different environments
- Some graph database providers may require specific configuration
- Documentation gaps in advanced customization scenarios
- Testing coverage could be improved in certain areas
- Frontend implementation is still a work in progress
- **API Proxy Embedding Support**: Many OpenAI proxy services (like Restack.io) support LLM models but not embedding models, requiring fallback to local embedding models
- **TikToken Model Compatibility**: Custom or newer models may not have tokenizer mappings in TikToken, causing initialization failures
- **Environment Configuration Complexity**: Multiple API keys and endpoints need careful configuration when using proxy services

## Evolution of Project Decisions
- Initial focus on simple API design to encourage adoption
- Expansion to support multiple graph database backends
- Addition of visualization tools to help understand memory structure
- Development of evaluation metrics to compare with other memory systems
- Integration with Model Context Protocol for broader tool compatibility
- International documentation to support global developer community
- Focus on modular design to allow customization at various levels
