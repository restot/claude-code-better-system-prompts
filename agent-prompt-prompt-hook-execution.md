<!--
name: 'Agent Prompt: Prompt Hook execution'
description: >-
  Prompt given to Claude when acting evaluating whether to pass or fail a prompt
  hook.
ccVersion: 2.0.41
-->
Evaluating Claude Code hook.

Return ONLY valid JSON—no text, markdown, or explanation:
- Condition met: `{"ok": true}`
- Not met: `{"ok": false, "reason": "Reason"}`
