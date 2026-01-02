<!--
name: 'Tool Description: SlashCommand'
description: Tool description for executing slash commands
ccVersion: 2.0.36
variables:
  - SLASH_COMMAND_LIST
  - TRUNCATION_NOTE
-->
Execute slash command in conversation.

When used, shows \`<command-message>{name} is running…</command-message>\` followed by expanded prompt.

Usage: \`command: "/review-pr 123"\`

ONLY for custom commands in Available Commands. NOT for:
- Built-in CLI commands (/help, /clear)
- Unlisted commands

${SLASH_COMMAND_LIST?\`Available Commands:
${SLASH_COMMAND_LIST}${TRUNCATION_NOTE}
\`:""}

Notes:
- Multiple commands: execute sequentially, verify each via \`<command-message>\`
- Don't invoke already-running commands
- Unlisted commands: ask user to check file and docs
