# Setup Guide

This guide provides instructions for setting up and running the Damn Vulnerable Model Context Protocol (DVMCP) challenges.

## Prerequisites

- Python 3.10 or higher
- pip (Python package installer)
- A Model Context Protocol (MCP) client (e.g., Claude Desktop or MCP Inspector)

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/damn-vulnerable-mcs.git
   cd damn-vulnerable-mcs
   ```

2. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

## Running the Challenges

Each challenge is implemented as a standalone MCP server in its respective directory. To run a challenge:

1. Navigate to the challenge directory:
   ```
   cd challenges/easy/challenge1
   ```

2. Run the server:
   ```
   python server.py
   ```

3. The server will start and listen on a specific port (each challenge uses a different port):
   - Challenge 1: http://localhost:9001
   - Challenge 2: http://localhost:9002
   - Challenge 3: http://localhost:9003
   - Challenge 4: http://localhost:9004
   - Challenge 5: http://localhost:9005
   - Challenge 6: http://localhost:9006
   - Challenge 7: http://localhost:9007
   - Challenge 8: http://localhost:9008
   - Challenge 9: http://localhost:9009
   - Challenge 10: http://localhost:9010

4. Connect to the server using an MCP client:
   -  Cline refer https://docs.cline.bot/mcp-servers/connecting-to-a-remote-server Cine supports both tools and resources


## MCP Client Options

### Claude Desktop

Claude Desktop is a desktop application that allows you to interact with Claude and connect to MCP servers. You can download it from the Anthropic website.

To connect to a challenge server:
1. Open Claude Desktop
2. Click on the "Connect to MCP Server" option
3. Enter the server URL (e.g., http://localhost:8001)
4. Start interacting with the server through Claude

### MCP Inspector

The MCP Inspector is a development tool included with the MCP Python SDK. It allows you to inspect and interact with MCP servers.

To use the MCP Inspector:
1. Install the MCP Python SDK with the CLI tools:
   ```
   pip install "mcp[cli]"
   ```

2. Run the MCP Inspector:
   ```
   mcp dev http://localhost:8001
   ```

3. The inspector will connect to the server and allow you to explore its resources and tools

## Troubleshooting

### Port Conflicts

If you encounter port conflicts (e.g., "Address already in use"), you can modify the port number in the challenge's `server.py` file. Look for the line:

```python
uvicorn.run(mcp.app, host="0.0.0.0", port=8001)
```

Change the port number to an available port.

### Dependency Issues

If you encounter dependency issues, try creating a virtual environment:

```
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### Server Connection Issues

If you have trouble connecting to the server:
1. Ensure the server is running (you should see a message like "Server running at http://localhost:8001")
2. Check if there are any firewall issues blocking the connection
3. Verify that you're using the correct URL in your MCP client

## Next Steps

Once you have the challenges running, refer to the [Challenges Guide](challenges.md) for details on each challenge and hints for solving them.
