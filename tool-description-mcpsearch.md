<!--
name: 'Tool Description: MCPSearch'
description: Tool description for the MCPSearch tool
ccVersion: 2.0.70
-->
Search/select MCP tools to make them available.

**MANDATORY**: Load MCP tools with this BEFORE calling them. Unloaded tools will fail.

## Query Modes
1. **Direct selection**: \`select:<tool_name>\` when you know the tool
   - "select:mcp__slack__read_channel"
2. **Keyword search**: keywords when unsure
   - "slack message" → returns up to 5 matches

## Correct
<expample>
User: List files in src
[MCPSearch: "select:mcp__filesystem__list_directory"]
[Call MCP tool]
</expample>

## Wrong
<expample>
[Directly calls mcp__slack__read_channel without loading]
WRONG - Must load first
</expample>
