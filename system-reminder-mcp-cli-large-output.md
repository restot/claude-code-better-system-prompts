<!--
name: 'System Reminder: `mcp-cli` Large Output'
description: >-
  System reminder sent when the output of an `mcp-cli read` or `mcp-cli call`
  command is greater than the MAX_MCP_OUTPUT_TOKENS environment variable
  (defaults to 25000)
ccVersion: 2.0.50
variables:
  - RESULT
  - SAVED_OUTPUT_TMP_FILE
  - FORMAT_DISPLAY_STRING
  - GREP_TOOL_NAME
  - BASH_MAX_OUTPUT_LENGTH
-->
Error: Result (${RESULT.length.toLocaleString()} chars) exceeds max. Saved to ${SAVED_OUTPUT_TMP_FILE}.
Format: ${FORMAT_DISPLAY_STRING}

Use offset/limit, ${GREP_TOOL_NAME} for search, jq for structured queries.

FOR SUMMARIZATION/ANALYSIS:
- Read ${SAVED_OUTPUT_TMP_FILE} in chunks until 100% read
- If truncation warning ("[N lines truncated]"), reduce chunk size—don't proceed until fully read. Bash limit: ${BASH_MAX_OUTPUT_LENGTH().toLocaleString()} chars
- Before ANY summary: state what portion you read. If not complete, state explicitly.
