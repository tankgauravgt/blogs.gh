---
title: "01: Create MCP Server"
---
# Create First MCP Server

## Steps:

### 01: Install uv Package Manager

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### 02: Create Project

```bash
uv init
uv venv
source .venv/bin/activate # (or `.venv\Scripts\activate` in windows)
uv add "mcp[cli]"
```

### 03: Write Supported Tools 

```python
import os
import subprocess
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("terminal")
DEFAULT_WORKSPACE = os.path.expanduser("~/mcp/workspace")

@mcp.tool()
async def run_command(command):
    try:
        result = subprocess.run(
	        command, 
	        shell=True, 
	        cwd=DEFAULT_WORKSPACE, 
	        capture_output=True, 
	        text=True
	    )
        return result.stdout or result.stderr
    except Exception as e:
        return str(e)

if __name__ == "__main__":
    mcp.run(transport='stdio')
```

### 04: Use in MCP Client

```json
{
    "mcpServers": {
        "terminal": {
            "command": "/Users/tankgauravgt/.local/bin/uv", 
            "args": [
                "--directory", 
                "/Users/tankgauravgt/mcp/servers/terminal_server", 
                "run",
                "terminal_server.py"
            ]
        }
    }
}
```

## References:

- Kartik Marwah
	- https://github.com/theailanguage/terminal_server
	- https://www.linkedin.com/in/kartikmarwah
	- https://github.com/theailanguage
