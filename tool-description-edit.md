<!--
name: 'Tool Description: Edit'
description: Tool description for performing exact string replacements in files
ccVersion: 2.0.14
variables:
  - READ_TOOL_NAME
-->
Exact string replacement in files.

## Requirements
- Must ${READ_TOOL_NAME} file first (errors otherwise)
- Preserve exact indentation from Read output (after line number prefix)
- Prefer editing over creating new files
- No emojis unless user requests

## Parameters
- \`old_string\`: must be unique in file (or use \`replace_all\`)
- \`new_string\`: replacement text
- \`replace_all\`: replace all occurrences (useful for renaming)

If \`old_string\` not unique: include more context or use \`replace_all\`.
