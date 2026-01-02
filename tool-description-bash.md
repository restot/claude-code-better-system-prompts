<!--
name: 'Tool Description: Bash'
description: 'Description for the Bash tool, which allows Claude to run shell commands'
ccVersion: 2.0.25
variables:
  - CUSTOM_TIMEOUT_MS
  - MAX_TIMEOUT_MS
  - MAX_OUTPUT_CHARS
  - BASH_TOOL_NAME
  - BASH_TOOL_EXTRA_NOTES
  - SEARCH_TOOL_NAME
  - GREP_TOOL_NAME
  - READ_TOOL_NAME
  - EDIT_TOOL_NAME
  - WRITE_TOOL_NAME
  - GIT_COMMIT_AND_PR_CREATION_INSTRUCTION
-->
Execute bash commands in persistent shell with optional timeout.

**Use for**: git, npm, docker, system operations
**NOT for**: file operations (use specialized tools instead)

## Before Executing
1. **Directory check**: Use `ls` to verify parent directory before creating files/dirs
2. **Quote paths with spaces**: `cd "/path/with spaces"` (not `cd /path/with spaces`)

## Usage
- Required: command
- Optional: timeout (up to ${CUSTOM_TIMEOUT_MS()}ms, default ${MAX_TIMEOUT_MS()}ms)
- Include 5-10 word description
- Output truncated at ${MAX_OUTPUT_CHARS()} chars
- `run_in_background`: run async, monitor via ${BASH_TOOL_NAME}
${BASH_TOOL_EXTRA_NOTES()}

## Avoid These Commands (use tools instead)
- find/ls → ${SEARCH_TOOL_NAME}
- grep/rg → ${GREP_TOOL_NAME}
- cat/head/tail → ${READ_TOOL_NAME}
- sed/awk → ${EDIT_TOOL_NAME}
- echo >/cat <<EOF → ${WRITE_TOOL_NAME}

## Multiple Commands
- Independent: parallel ${BASH_TOOL_NAME} calls
- Dependent: chain with `&&` (e.g., `git add . && git commit -m "msg"`)
- Use `;` only when failure doesn't matter
- No newlines between commands

## Working Directory
Use absolute paths; avoid `cd` unless user requests it.

${GIT_COMMIT_AND_PR_CREATION_INSTRUCTION()}
