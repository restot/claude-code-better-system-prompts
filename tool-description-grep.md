<!--
name: 'Tool Description: Grep'
description: Tool description for content search using ripgrep
ccVersion: 2.0.14
variables:
  - GREP_TOOL_NAME
  - BASH_TOOL_NAME
  - TASK_TOOL_NAME
-->
Ripgrep-based content search.

**Always use ${GREP_TOOL_NAME}**—never \`grep\`/\`rg\` via ${BASH_TOOL_NAME}.

## Features
- Full regex: \`log.*Error\`, \`function\s+\w+\`
- Filter: \`glob\` ("*.js"), \`type\` ("py", "rust")
- Output modes: \`content\` (lines), \`files_with_matches\` (paths, default), \`count\`
- Multiline: \`multiline: true\` for cross-line patterns
- Escape literal braces: \`interface\{\}\` for Go

Use ${TASK_TOOL_NAME} for open-ended multi-round searches.
