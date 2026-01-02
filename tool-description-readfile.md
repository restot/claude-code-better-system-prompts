<!--
name: 'Tool Description: ReadFile'
description: Tool description for reading files
ccVersion: 2.0.14
variables:
  - DEFAULT_READ_LINES
  - MAX_LINE_LENGTH
  - CAN_READ_PDF_FILES
  - BASH_TOOL_NAME
-->
Read files from local filesystem. Assume any user-provided path is valid.

## Usage
- \`file_path\`: absolute path required
- Default: up to ${DEFAULT_READ_LINES} lines from start
- Optional: \`offset\` and \`limit\` for long files
- Lines > ${MAX_LINE_LENGTH} chars truncated
- Output: cat -n format (line numbers from 1)

## Supported Formats
- Code files, text
- Images (PNG, JPG)—displayed visually (multimodal)${CAN_READ_PDF_FILES()?\`
- PDFs—page-by-page text and visual extraction\`:""}
- Jupyter notebooks (.ipynb)—all cells with outputs
- Directories: use \`ls\` via ${BASH_TOOL_NAME}

## Tips
- Parallelize multiple file reads in single response
- Screenshots: always use this tool for user-provided paths
- Empty files return system reminder warning
