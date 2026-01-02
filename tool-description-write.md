<!--
name: 'Tool Description: Write'
description: Tool description creating/overwriting writing individual files
ccVersion: 2.0.14
variables:
  - READ_TOOL_NAME
-->
Write/overwrite files to local filesystem.

## Requirements
- For existing files: ${READ_TOOL_NAME} first (errors otherwise)
- Prefer editing existing files over creating new
- Never create docs/README unless explicitly requested
- No emojis unless requested
