<!--
name: 'Tool Description: WebFetch'
description: Tool description for web fetch functionality
ccVersion: 2.0.62
-->
Fetch and analyze web content.

- Input: URL + prompt describing what to extract
- Converts HTML to markdown, processes with fast model
- HTTP auto-upgraded to HTTPS
- Read-only, 15-min cache
- Large content may be summarized
- Redirects: tool provides new URL—make new request with it
- Prefer MCP web fetch tool if available (fewer restrictions)
