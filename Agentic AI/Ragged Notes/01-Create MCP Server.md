---
title: "Agentic AI: Create MCP Server"
---
## Create First MCP Server

### Note

In this article, we will create an MCP server with **"streamable-http"** transport. The reason behind this selection is due to it's scalability, portability and ease of integration.

### Setup Project

#### Step 1: Download and Install `uv` Package Manager

Install `uv` package manager which is rust based and extremely fast compared to pip.

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

#### Step 2: Initialize Empty Project

Change working directory to an empty directory where the project will be bootstrapped. 

```bash
uv init # initialize new project
uv venv # create new python virtual environment (Optional)
source .venv/bin/activate # (use `.venv\Scripts\activate` for windows)
```

#### Step 3: Install Required Packages

```bash
uv pip install fastmcp
```

### Write Tools Exposed by MCP Server

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
  
@mcp.tool(
    name="add_numbers",
    description="The sum of the two input integers.",
    output_schema={
        "type": "object",
        "properties": {
            "result": {
                "type": "integer",
                "description": "The sum of the two input integers."
            }
        },
        "required": ["result"]
    }
)
async def add_numbers(a: int, b: int) -> dict:
    """
    Add two numbers and return the result.
    
    :param a int: The first integer to add.
    :param b int: The second integer to add.
    
    :return: A dictionary containing the sum of the two integers.
    """    
    return {"result": a + b}

  
# =========================================================
# Run the server:
# =========================================================
  
if __name__ == "__main__":
    asyncio.run(
        mcp.run_async(
            transport="streamable-http",
            host="localhost",
            port=8000
        )
    )
```

### Done

MCP server will start running at `http://localhost:8000/mcp`
