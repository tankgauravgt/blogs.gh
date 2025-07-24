---
title: "01: Create MCP Server"
---
# Create First MCP Server

## Steps

### 01: Install uv Package Manager

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

### 02: Create Project

```bash
uv init
uv venv
source .venv/bin/activate # (or `.venv\Scripts\activate` in windows)
uv pip install fastmcp
```

### 03: Write Supported Tools 

```python
from fastmcp import FastMCP
import asyncio

# =========================================================
# Create MCP server:
# =========================================================

mcp = FastMCP()

# =========================================================
# Define tools:
# =========================================================

@mcp.tool(output_schema={
    "type": "object",
    "properties": {
        "result": {
            "type": "integer",
            "description": "The sum of the two input integers."
        }
    },
    "required": ["result"]
})
def add(a: int, b: int) -> int:
    """Add two numbers and return the result."""
    return {"result": a + b}

# =========================================================
# Run the server:
# =========================================================

if __name__ == "__main__":
    asyncio.run(
        mcp.run_async(
            transport="streamable-http",
            host="localhost",
            port=8000,
        )
    )
```

### 04: Use in MCP Client

MCP server should be now running at `http://localhost:8000/mcp`
