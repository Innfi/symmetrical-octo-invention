#AI #Automation

>[!tip]
>an open standard that allows AI applications—such as large language models (LLMs), chatbots, and agent platforms—to seamlessly connect with external tools, data sources, and systems using a common framework

![concept](https://mintcdn.com/mcp/4ZXF1PrDkEaJvXpn/images/mcp-simple-diagram.png?w=840&fit=max&auto=format&n=4ZXF1PrDkEaJvXpn&q=85&s=8b44b031c68d1c10fb0c443f09d237f1)

[[MCP Server]]
## Lifecycle 
- https://modelcontextprotocol.io/specification/2025-06-18/basic/lifecycle
## Sequence
- initialize
- initialized
- tools/list
- tools/call
## Transport 
- stdio
- [[Streaming HTTP]]
- [[SSE]]
## Data format
- JSON-RPC 2.0
## Tool
- [[MCP Inspector]]
- mastra
- dify
