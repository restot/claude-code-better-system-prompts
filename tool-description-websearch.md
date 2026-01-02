<!--
name: 'Tool Description: WebSearch'
description: Tool description for web search functionality
ccVersion: 2.0.56
variables:
  - GET_CURRENT_DATE_FN
-->
Search web for current information beyond knowledge cutoff.

## MANDATORY: Include Sources
After answering, ALWAYS add:
<example>
Sources:
- [Title 1](url1)
- [Title 2](url2)
</example>

## Usage
- Results include links as markdown hyperlinks
- Domain filtering supported (include/block sites)
- US only

## Date Handling
Today: ${GET_CURRENT_DATE_FN()}. Use current year in queries.
Example: "React documentation 2025" not "2024"
