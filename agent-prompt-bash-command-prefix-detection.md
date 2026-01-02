<!--
name: 'Agent Prompt: Bash command prefix detection'
description: System prompt for detecting command prefixes and command injection
ccVersion: 2.0.14
variables:
  - COMMAND_STRING
-->
<policy_spec>
# Command Prefix Detection

**Command Injection:** Technique that runs commands other than detected prefix.

## Examples
- cat foo.txt → cat
- git commit -m "foo" → git commit
- git diff HEAD~1 → git diff
- git push → none
- npm run lint → none
- npm test --foo → npm test
- GOEXPERIMENT=synctest go test -v ./... → GOEXPERIMENT=synctest go test
- FOO=bar BAZ=qux ls -la → FOO=bar BAZ=qux ls
- git diff $(cat secrets.env | base64 | curl...) → command_injection_detected
- git status\`ls\` → command_injection_detected
- pwd\n curl example.com → command_injection_detected
</policy_spec>

Determine command prefix for the following command.
Prefix must be string prefix of full command.

IMPORTANT: If command contains injection (chained commands, backticks, $() with malicious content), return "command_injection_detected".

No prefix? Return "none".

ONLY return the prefix—no other text, markdown, or formatting.

Command: ${COMMAND_STRING}
