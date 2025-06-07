# MCP Servers Global Configuration

All four requested MCP servers have been successfully added to your global Cursor configuration at `~/.cursor/mcp.json`.

## Installed MCP Servers

### 1. Crawl4AI RAG (@coleam00/mcp-crawl4ai-rag)
- **Purpose**: Web crawling and RAG (Retrieval-Augmented Generation) capabilities
- **Features**: 
  - Advanced web scraping with Crawl4AI
  - Vector database storage using Supabase
  - RAG strategies including contextual embeddings, hybrid search, agentic RAG, and reranking
- **Configuration Required**: 
  - `OPENAI_API_KEY`: Your OpenAI API key for embeddings and LLM operations
  - `SUPABASE_URL`: Your Supabase project URL
  - `SUPABASE_SERVICE_KEY`: Your Supabase service key
- **Note**: You'll need to set up a Supabase database with pgvector extension and create the necessary tables

### 2. Context7 (@upstash/context7-mcp)
- **Purpose**: Provides up-to-date documentation and code examples for 9000+ libraries
- **Features**:
  - Fetches latest docs directly from official sources
  - Prevents hallucinated or outdated code
  - Version-specific documentation
- **Usage**: Add "use context7" to your prompts when you need current library documentation
- **No additional configuration required**

### 3. Docfork (docfork)
- **Purpose**: Fresh documentation for 9000+ libraries (similar to Context7)
- **Features**:
  - Daily refreshed documentation
  - Accurate examples from current docs
  - Fast retrieval of library information
- **Usage**: Add "use docfork" to your prompts when you need library documentation
- **No additional configuration required**

### 4. Sequential Thinking (@modelcontextprotocol/server-sequential-thinking)
- **Purpose**: Structured problem-solving through sequential thinking
- **Features**:
  - Breaks down complex problems into manageable steps
  - Supports revision and refinement of thoughts
  - Allows branching into alternative reasoning paths
  - Dynamic adjustment of thinking process
- **Usage**: Helps with complex problem-solving, planning, and analysis tasks
- **No additional configuration required**

## Usage

After restarting Cursor, these MCP servers will be available. You can:

1. **For Crawl4AI RAG**: First configure your API keys in the configuration file, then use it for web scraping and RAG operations
2. **For Context7**: Include "use context7" in your prompts when asking about any programming library
3. **For Docfork**: Include "use docfork" in your prompts for library documentation
4. **For Sequential Thinking**: The server will help break down complex problems automatically

## Important Notes

1. **Restart Cursor** after configuration changes for them to take effect
2. **API Keys**: Remember to replace the placeholder API keys in the configuration with your actual keys for crawl4ai-rag
3. **Backup**: A backup of your configuration has been created at `~/.cursor/mcp.json.backup`

## Troubleshooting

If any server fails to start:
- Check that Node.js is installed and accessible
- Try using `bunx` instead of `npx` if you encounter module resolution issues
- Check the Cursor logs for specific error messages
- Ensure all required environment variables are properly set (especially for crawl4ai-rag)