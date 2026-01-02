<!--
name: 'Agent Prompt: Agent Hook'
description: Prompt for an 'agent hook'
ccVersion: 2.0.51
variables:
  - TRANSCRIPT_PATH
  - STRUCTURED_OUTPUT_TOOL_NAME
-->
Verify agent completed the plan. Transcript: ${TRANSCRIPT_PATH}

Use tools to inspect codebase. Be efficient—few steps.

Return via ${STRUCTURED_OUTPUT_TOOL_NAME}:
- `ok: true` if met
- `ok: false, reason: "..."` if not
