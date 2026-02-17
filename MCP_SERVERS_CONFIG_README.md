# MCP Servers Configuration Guide

This document provides a comprehensive JSON configuration file (`mcp-servers-config.json`) for 78 MCP (Model Context Protocol) servers, derived from the official MCP servers repository at https://github.com/modelcontextprotocol/servers.

## Overview

The configuration file contains settings for the following MCP servers:

### Reference Servers
- **Sequential Thinking** - Dynamic and reflective problem-solving through thought sequences
- **Memory** - Knowledge graph-based persistent memory system
- **Server Memory** - Same as Memory (both use `@modelcontextprotocol/server-memory`; included for compatibility)

### Database Servers
- **PostgreSQL** - Read-only database access with schema inspection
- **SQLite** - Database interaction and business intelligence capabilities
- **MariaDB** - Standard interface for managing and querying MariaDB databases
- **MongoDB** - Support for both MongoDB Community Server and MongoDB Atlas
- **SQL Server** - Official Microsoft SQL Server MCP
- **Redis** - Interact with Redis key-value stores
- **Redis Cloud API** - Manage Redis Cloud resources using natural language
- **Neo4j** - Neo4j graph database server (schema + read/write-cypher)
- **Neo4j GDS** - Neo4j graph data science server with comprehensive graph algorithms
- **Neo4j Agent Memory** - Memory management for AI agents using Neo4j knowledge graphs
- **Astra DB** - Tools for managing collections and documents in DataStax Astra DB
- **Neon** - Interact with the Neon serverless Postgres platform
- **Oracle** - Official Oracle Database: SQLcl MCP server
- **Memgraph** - Query your data in Memgraph graph database
- **Milvus** - Search, Query and interact with data in your Milvus Vector Database
- **Qdrant** - Implement semantic memory layer on top of the Qdrant vector search engine
- **Supabase** - Interact with Supabase: Create tables, query data, deploy edge functions

### Development & CI/CD Servers
- **GitHub** - Repository management, file operations, and GitHub API integration
- **GitLab** - GitLab API, enabling project management
- **Azure DevOps** - Interact with Azure DevOps services
- **Jenkins** - Official Jenkins MCP Server plugin
- **JetBrains** - Work on your code with JetBrains IDEs
- **JFrog** - MCP Server for the JFrog Platform API
- **Render** - Spin up new services, run queries, and debug rapidly
- **Vercel** - Access logs, search docs, and manage projects and deployments
- **Linear** - Search, create, and update Linear issues, projects, and comments
- **Pulumi** - Deploy and manage cloud infrastructure using Pulumi
- **Terraform** - Integrate with Terraform ecosystem for Infrastructure as Code

### Cloud & Infrastructure Servers
- **Azure** - Access to key Azure services and tools
- **Google Cloud Run** - Deploy code to Google Cloud Run
- **Databricks** - Connect to data, AI tools & agents, and the Databricks platform
- **Firebase** - Firebase's experimental MCP Server to power your AI Tools
- **E2B** - Run code in secure sandboxes hosted by E2B

### API & Integration Servers
- **Stripe** - Interact with Stripe API for payments
- **Zapier** - Connect your AI Agents to 8,000 apps instantly
- **Make** - Turn your Make scenarios into callable tools for AI assistants
- **Postman API** - Manage your Postman resources using the Postman API
- **Alpaca** - Trade stocks and options, analyze market data through Alpaca's Trading API
- **Canva** - AI-powered development assistance for Canva apps and integrations
- **Notion** - MCP server for the Notion API
- **Hugging Face** - Connect to the Hugging Face Hub APIs programmatically

### Monitoring & Analytics Servers
- **Sentry** - Retrieving and analyzing issues from Sentry.io
- **Grafana** - Search dashboards, investigate incidents and query datasources
- **Microsoft Clarity** - Get your behavioral analytics data and insights from Clarity
- **Raygun** - Interact with your crash reporting and real user monitoring data

### Search & Data Extraction Servers
- **Brave Search** - Web and local search using Brave's Search API
- **Perplexity** - Connects to Perplexity's Sonar API for real-time web-wide research
- **Firecrawl** - Extract web data with Firecrawl
- **Pure.md** - Access web content in markdown format
- **CoinGecko** - Official CoinGecko API MCP Server for Crypto Price & Market Data
- **Coinex** - Interface with the CoinEx cryptocurrency exchange
- **Polymarket** - Real-time prediction market data from Polymarket
- **BuiltWith** - Identify the technology stack behind any website
- **IP2Location.io** - Retrieve geolocation information for an IP address

### Browser Automation Servers
- **Puppeteer** - Browser automation and web scraping
- **Playwright** - Browser automation using Playwright
- **Browserbase** - Automate browser interactions in the cloud
- **Chrome DevTools** - Enable AI coding assistants to debug web pages directly in Chrome

### Security & Testing Servers
- **Burp Suite** - MCP Server extension allowing AI clients to connect to Burp Suite
- **BoostSecurity** - Guardrails coding agents against introducing dependencies with vulnerabilities

### AI & ML Servers
- **Claude Context** - Bring your codebase as context to Claude Code
- **PaddleOCR** - Enterprise-grade OCR and document parsing capabilities
- **Behavioral Prediction** - AI-powered tools to analyze wallet behaviour prediction

### Documentation & Learning Servers
- **Microsoft Learn Docs** - Structured access to Microsoft's official documentation

### Specialized Servers
- **Hive Intelligence** - Ultimate cryptocurrency MCP for AI assistants
- **Parallel Task MCP** - Initiate Deep Research and Batch Tasks
- **Persona Sessions** - Conduct structured, persona-driven sessions
- **Pinecone** - Search documentation and manage data
- **Ramp** - Interact with Ramp's Developer API
- **Upstash** - Manage Redis databases and run Redis commands on Upstash
- **Plugged.in** - Comprehensive proxy that combines multiple MCP servers
- **PIA** - AI-friendly access to U.S. Government Open Datasets
- **LinkedIn MCP Runner** - Write, edit, and schedule LinkedIn posts
- **MCP Discovery** - Lightweight CLI tool for discovering MCP server capabilities

## Usage

### For Claude Desktop

1. Copy the entire content from `mcp-servers-config.json`
2. Paste it into your Claude Desktop configuration file:
   - **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
   - **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

### For Other MCP Clients

Different MCP clients may have different configuration file locations. Consult your client's documentation for the correct location.

### Customizing the Configuration

Before using the configuration, you need to:

1. **Replace placeholder values**: Many servers require API keys, tokens, or connection strings. Replace all `<YOUR_*>` placeholders with your actual credentials.

2. **Remove unused servers**: You don't need to include all 78 servers. Remove the ones you don't plan to use to keep your configuration clean.

3. **Update paths and URLs**: Some servers require local file paths or specific URLs. Update these according to your environment.

### Example: Configuring a Subset of Servers

Here's an example configuration with just a few servers properly configured:

```json
{
  "mcpServers": {
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_actual_token_here"
      }
    },
    "sqlite": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sqlite", "/path/to/your/database.db"]
    }
  }
}
```

## Environment Variables

Many servers require environment variables for authentication and configuration. Common patterns include:

- **API Keys**: `*_API_KEY`, `*_API_SECRET`
- **Access Tokens**: `*_ACCESS_TOKEN`, `*_TOKEN`, `*_PAT`
- **Connection Strings**: `*_URI`, `*_URL`, `*_CONNECTION_STRING`
- **Credentials**: `*_USER`, `*_PASSWORD`

### Security Best Practices

1. **Never commit credentials**: Don't commit configuration files with real credentials to version control
2. **Use environment variables**: Consider using your system's environment variables instead of hardcoding credentials
3. **Rotate keys regularly**: Regularly rotate API keys and access tokens
4. **Principle of least privilege**: Only grant necessary permissions to each service

## Package Installation

Most servers in this configuration use `npx` which automatically downloads and runs the latest version of the package. Some servers may require:

- **Python servers**: Install with `uvx` or `pip`
- **.NET servers**: Require `dotnet` runtime
- **Java servers**: Require Java runtime
- **Rust servers**: May need to be installed separately

## Troubleshooting

### Server Not Starting

1. Check that all required environment variables are set
2. Verify that the package name is correct
3. Ensure you have internet connectivity for `npx` to download packages
4. Check the server's GitHub repository for specific installation instructions

### Authentication Errors

1. Verify that your API keys and tokens are correct
2. Check that the tokens have the necessary permissions
3. Ensure tokens haven't expired

### Connection Errors

1. Verify that service URLs are correct
2. Check that the services are running (for local services)
3. Verify network connectivity to external services

## Additional Resources

- [MCP Official Documentation](https://modelcontextprotocol.io/)
- [MCP Servers Repository](https://github.com/modelcontextprotocol/servers)
- [MCP Registry](https://registry.modelcontextprotocol.io/)
- Individual server documentation (linked in GitHub repositories)

## Contributing

To add new servers or update existing ones:

1. Find the server's GitHub repository
2. Check the installation instructions
3. Add the configuration following the existing pattern
4. Test the configuration
5. Submit a pull request

## License

This configuration file is provided as-is. Refer to individual server repositories for their respective licenses.

## Notes

- Not all servers listed may be production-ready
- Some servers are experimental or in beta
- Package names and installation methods may change over time
- Always refer to the official documentation for the most up-to-date information
- Some servers may require paid subscriptions or API access
- **Note on Memory vs Server-Memory**: Both `memory` and `server-memory` in the configuration use the same package (`@modelcontextprotocol/server-memory`). They are included separately for compatibility with the problem statement requirements, but they provide identical functionality. You can remove one if desired.

---

**Last Updated**: February 2026  
**Source**: https://github.com/modelcontextprotocol/servers
