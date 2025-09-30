# My MCP Server

A simple Model Context Protocol (MCP) server that provides an addition tool for adding two numbers together.

## Overview

This MCP server implements a basic arithmetic tool that can add two numbers. It's built using the official MCP SDK and demonstrates how to create a custom MCP server.

## Features

- **Addition Tool**: Adds two numbers together
- **MCP Protocol**: Follows the Model Context Protocol specification
- **Type Safety**: Uses Zod for input validation

## Installation

1. Clone or download this repository
2. Install dependencies:
   ```bash
   npm install
   ```

## Usage

### Running the Server

To run the MCP server:

```bash
node mcp.js
```

The server will start and listen for MCP protocol messages via stdio.

### Available Tools

#### Addition Tool

- **Name**: `add`
- **Description**: Add two numbers together
- **Parameters**:
  - `a` (number): First number
  - `b` (number): Second number
- **Returns**: The sum of the two numbers as text

### Example Usage

When connected to an MCP client, you can use the addition tool like this:

```json
{
  "tool": "add",
  "parameters": {
    "a": 5,
    "b": 3
  }
}
```

This would return: `8`

## Adding to Cursor

To use this MCP server in Cursor, you need to configure it in your Cursor settings:

### Method 1: Using Cursor Settings UI

1. **Open Cursor Settings**:

   - Press `Cmd+,` (Mac) or `Ctrl+,` (Windows/Linux)
   - Or go to `Cursor > Preferences > Settings`

2. **Navigate to MCP Settings**:

   - Search for "MCP" in the settings search bar
   - Click on "Model Context Protocol" settings

3. **Add the Server**:
   - Click "Add Server" or the "+" button
   - Configure the server with these settings:
     ```
     Name: Addition Server
     Command: node
     Args: [path/to/your/mcp.js]
     Cwd: [path/to/your/project/directory]
     ```

### Method 2: Using Settings JSON

1. **Open Cursor Settings JSON**:

   - Press `Cmd+Shift+P` (Mac) or `Ctrl+Shift+P` (Windows/Linux)
   - Type "Preferences: Open Settings (JSON)"
   - Select it

2. **Add MCP Configuration**:
   Add this configuration to your settings JSON:

   ```json
   {
     "mcp.servers": {
       "addition-server": {
         "command": "node",
         "args": ["/Users/slav/Documents/dev/first-mcp/mcp.js"],
         "cwd": "/Users/slav/Documents/dev/first-mcp"
       }
     }
   }
   ```

   **Important**: Replace the paths with your actual project directory path.

3. **Restart Cursor**:
   - Close and reopen Cursor for the changes to take effect

### Using the Addition Tool in Cursor

Once configured, you can use the addition tool in Cursor by:

1. **Opening a chat** with the AI assistant
2. **Asking it to add numbers**: "Can you add 15 and 27 for me?"
3. **The AI will use your MCP server** to perform the calculation

### Troubleshooting

- **Server not found**: Make sure the path to `mcp.js` is correct and the file exists
- **Permission errors**: Ensure you have execute permissions on the Node.js binary
- **Dependencies missing**: Run `npm install` in the project directory first
- **Port conflicts**: This server uses stdio, so no port conflicts should occur

## Development

### Project Structure

- `mcp.js` - Main server implementation
- `package.json` - Node.js project configuration
- `README.md` - This file

### Dependencies

- `@modelcontextprotocol/sdk` - Official MCP SDK
- `zod` - Type validation library

## License

ISC
