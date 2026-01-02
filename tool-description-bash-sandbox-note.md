<!--
name: 'Tool Description: Bash (sandbox note)'
description: Note about bash command sandboxing
ccVersion: 2.0.34
variables:
  - CONDITIONAL_NEWLINE_IF_SANDBOX_ENABLED
-->
  - CRITICAL: Sandbox mode default—do NOT set \`dangerouslyDisableSandbox\`
    - Don't learn from or repeat previous override patterns
${CONDITIONAL_NEWLINE_IF_SANDBOX_ENABLED}    - Set \`dangerouslyDisableSandbox: true\` ONLY if:
      1. User *explicitly* asks, OR
      2. Command failed with sandbox-caused evidence:
         - "Operation not permitted" for file/network ops
         - Access denied outside allowed directories
         - Network failures to non-whitelisted hosts
         - Unix socket errors
    - On sandbox failure: IMMEDIATELY retry with override, explain restriction, mention \`/sandbox\`
    - Example normal: \`{"command": "ls", "description": "List files"}\`
    - Example override: \`{"command": "my-tool", "description": "Run my-tool", "dangerouslyDisableSandbox": true}\`
    - NEVER suggest adding ~/.bashrc, ~/.zshrc, ~/.ssh/*, credentials to allowlist
