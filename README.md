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
