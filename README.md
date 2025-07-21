# Model Context Protocol Servers - Oppie Compatible

This repository contains actively maintained implementations of [Model Context Protocol](https://modelcontextprotocol.io/) (MCP) servers. These servers were forked from the original archived repository and are now being actively maintained and improved with full [Oppie](https://oppie.ai) compatibility.

## 🚀 Powered by Oppie - One Integration, 300+ AI Superpowers

### Why Oppie for MCP Servers?

Traditional MCP server setup is complex: managing OAuth flows, storing API keys locally, configuring each server individually, and dealing with resource-hungry local processes. **Oppie eliminates all of this.**

#### For Developers:
- **Zero-Config Deployment**: Skip the OAuth implementation, token management, and configuration files
- **Cloud-Native Architecture**: All MCP servers run in Oppie's optimized cloud infrastructure
- **Unified Secret Management**: Enterprise-grade credential vault with automatic key rotation
- **Natural Language Permissions**: Define access controls in plain English, get precise RBAC automatically
- **Auto-Sync Across Clients**: Changes propagate instantly to Claude, Cursor, and all MCP-compatible tools

#### Technical Benefits:
- **Performance**: Zero local CPU/RAM usage - your dev machine stays lean
- **Security**: Credentials never touch your filesystem - encrypted at rest in cloud vaults  
- **Scalability**: Run 1 or 100 MCP servers simultaneously without infrastructure changes
- **Observability**: Built-in logging, metrics, and debugging tools for every server
- **Reliability**: Automatic retries, rate limit handling, and failover built-in

## 🛠️ Getting Started with Oppie

### Option 1: Oppie Desktop (Recommended)
The easiest way to use these MCP servers with Oppie:

1. **Download Oppie Desktop**: [Download for your platform](https://api.oppie.ai/api/oppie-desktop/download)
2. **Sign in**: Use your Oppie account or create one
3. **Browse & Install**: Click any MCP server to install it instantly
4. **Done!** Your AI clients now have access to all installed servers

### Option 2: Oppie Bridge (Advanced)
For developers who prefer manual configuration:

```bash
# Download the Oppie Bridge for your platform
curl -L https://api.oppie.ai/api/oppie-bridge/download -o oppie-bridge
chmod +x oppie-bridge

# Configure your MCP client (e.g., Claude Desktop)
{
  "mcpServers": {
    "oppie-gateway": {
      "command": "/path/to/oppie-bridge",
      "args": ["--token", "YOUR_OPPIE_TOKEN"]
    }
  }
}
```

## ✅ Oppie Compatibility Status

| MCP Server | Oppie Compatible | One-Click Deploy | OAuth Handled | Cloud Performance | Natural Language Config |
|------------|------------------|------------------|---------------|-------------------|------------------------|
| **AWS KB Retrieval** | ✅ | ✅ | ✅ | ⚡ Optimized | ✅ |
| **Brave Search** | ✅ | ✅ | ✅ | ⚡ Cached | ✅ |
| **EverArt** | ✅ | ✅ | ✅ | ⚡ GPU-powered | ✅ |
| **GitHub** | ✅ | ✅ | ✅ | ⚡ Rate-limit managed | ✅ |
| **GitLab** | ✅ | ✅ | ✅ | ⚡ Auto-scaled | ✅ |
| **Google Drive** | ✅ | ✅ | ✅ | ⚡ Edge cached | ✅ |
| **Google Maps** | ✅ | ✅ | ✅ | ⚡ Geo-distributed | ✅ |
| **PostgreSQL** | ✅ | ✅ | ✅ | ⚡ Connection pooled | ✅ |
| **Puppeteer** | ✅ | ✅ | N/A | ⚡ Headless cluster | ✅ |
| **Redis** | ✅ | ✅ | ✅ | ⚡ Managed cluster | ✅ |
| **Slack** | ✅ | ✅ | ✅ | ⚡ WebSocket pooled | ✅ |

### What Oppie Compatibility Means:
- **🚀 One-Click Deploy**: Install any server instantly through Oppie Desktop
- **🔐 OAuth Handled**: Never manage API keys or OAuth flows manually
- **⚡ Cloud Performance**: All processing happens in Oppie's cloud - zero local resource usage
- **🎯 Natural Language Config**: Configure permissions in plain English (e.g., "Give read-only access to my work repos")
- **🔄 Auto-Sync**: Changes instantly propagate to all your AI clients

## 🏗️ Oppie Architecture for Developers

### How Oppie Works
Oppie acts as a gateway between your AI clients and MCP servers, handling all the complexity:

```
AI Client (Claude/Cursor) ← → Oppie Bridge ← → Oppie Cloud ← → MCP Servers
                          (local binary)      (gateway)      (300+ servers)
```

### Key Technical Features

#### 1. Protocol Translation
- **MCP over stdio**: Your AI client communicates normally via stdio
- **HTTP Streamable/SSE**: Oppie Bridge uses modern protocols to the cloud
- **Automatic failover**: Seamless fallback between transport protocols

#### 2. Security Architecture
- **Zero Trust**: Credentials never stored locally
- **Token-based Auth**: Short-lived tokens with automatic refresh
- **Encrypted Transport**: TLS 1.3 for all communications
- **Audit Logging**: Every action tracked for compliance

#### 3. Performance Optimization
- **Edge Computing**: MCP servers run near your location
- **Connection Pooling**: Reused connections for low latency
- **Smart Caching**: Frequently accessed data cached at edge
- **Rate Limit Management**: Automatic handling across all services

#### 4. Developer Experience
- **Type-Safe APIs**: Full TypeScript support
- **Comprehensive SDKs**: JavaScript, Python, Go clients available
- **Rich Debugging**: Detailed logs and error traces
- **API Versioning**: Backward compatibility guaranteed

## Available Servers

The following servers are included in this repository:

- **[AWS KB Retrieval](https://github.com/OppieAI/mcp-servers/blob/main/src/aws-kb-retrieval-server/README.md)** - Integration with AWS Knowledge Base
- **[Brave Search](https://github.com/OppieAI/mcp-servers/blob/main/src/brave-search/README.md)** - Web search capabilities via Brave Search API
- **[EverArt](https://github.com/OppieAI/mcp-servers/blob/main/src/everart/README.md)** - AI art generation integration
- **[GitHub](https://github.com/OppieAI/mcp-servers/blob/main/src/github/README.md)** - GitHub API integration for repository management
- **[GitLab](https://github.com/OppieAI/mcp-servers/blob/main/src/gitlab/README.md)** - GitLab API integration for repository management
- **[Google Drive](https://github.com/OppieAI/mcp-servers/blob/main/src/gdrive/README.md)** - Google Drive file access and search (updated with simplified authentication)
- **[Google Maps](https://github.com/OppieAI/mcp-servers/blob/main/src/google-maps/README.md)** - Google Maps integration for location services
- **[PostgreSQL](https://github.com/OppieAI/mcp-servers/blob/main/src/postgres/README.md)** - PostgreSQL database connectivity
- **[Puppeteer](https://github.com/OppieAI/mcp-servers/blob/main/src/puppeteer/README.md)** - Web automation and scraping
- **[Redis](https://github.com/OppieAI/mcp-servers/blob/main/src/redis/README.md)** - Redis database connectivity
- **[Slack](https://github.com/OppieAI/mcp-servers/blob/main/src/slack/README.md)** - Slack workspace integration

## Getting Started

Each server has its own documentation in the respective `src/[server-name]/README.md` file. Please refer to the individual server documentation for setup and usage instructions.

## Contributing

We welcome contributions to improve these servers! Please feel free to:

- Submit bug reports and feature requests
- Contribute code improvements and new features
- Improve documentation
- Add new MCP servers

## License

MIT