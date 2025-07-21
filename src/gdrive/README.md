# Google Drive server

This MCP server integrates with Google Drive to allow listing, reading, and searching over files.

## Components

### Tools

- **search**
  - Search for files in Google Drive
  - Input: `query` (string): Search query
  - Returns file names and MIME types of matching files

### Resources

The server provides access to Google Drive files:

- **Files** (`gdrive:///<file_id>`)
  - Supports all file types
  - Google Workspace files are automatically exported:
    - Docs → Markdown
    - Sheets → CSV
    - Presentations → Plain text
    - Drawings → PNG
  - Other files are provided in their native format

## Getting started

### Prerequisites

1. Obtain a Google OAuth access token with the following scopes:
   - `https://www.googleapis.com/auth/drive.readonly` (or broader Drive access if needed)
   - `https://www.googleapis.com/auth/userinfo.profile`
   - `https://www.googleapis.com/auth/userinfo.email`

### Authentication

This server uses a simplified authentication approach that requires only an access token:

1. Set the `ACCESS_TOKEN` environment variable with your Google OAuth access token
2. Run the server: `node ./dist/index.js`

The server will authenticate using the provided access token without requiring OAuth client credentials or JSON files.

### Usage with Desktop App

To integrate this server with the desktop app, add the following to your app's server configuration:

#### Local Build

```json
{
  "mcpServers": {
    "gdrive": {
      "command": "node",
      "args": ["./dist/index.js"],
      "cwd": "/path/to/gdrive/server",
      "env": {
        "ACCESS_TOKEN": "your_google_oauth_access_token"
      }
    }
  }
}
```

#### Docker (if available)

```json
{
  "mcpServers": {
    "gdrive": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "-e", "ACCESS_TOKEN=your_google_oauth_access_token", "oppie/gdrive"]
    }
  }
}
```

### Usage with VS Code

Add the following JSON block to your User Settings (JSON) file in VS Code. You can do this by pressing `Ctrl + Shift + P` and typing `Preferences: Open User Settings (JSON)`.

Optionally, you can add it to a file called `.vscode/mcp.json` in your workspace. This will allow you to share the configuration with others.

> Note that the `mcp` key is not needed in the `.vscode/mcp.json` file.

#### Local Build

```json
{
  "mcp": {
    "servers": {
      "gdrive": {
        "command": "node",
        "args": ["./dist/index.js"],
        "cwd": "/path/to/gdrive/server",
        "env": {
          "ACCESS_TOKEN": "your_google_oauth_access_token"
        }
      }
    }
  }
}
```

## License

This MCP server is licensed under the MIT License. This means you are free to use, modify, and distribute the software, subject to the terms and conditions of the MIT License. For more details, please see the LICENSE file in the project repository.
