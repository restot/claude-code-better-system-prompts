<!--
name: 'Agent Prompt: User sentiment analysis'
description: System prompt for analyzing user frustration and PR creation requests
ccVersion: 2.0.14
variables:
  - CONVERSATION_HISTORY
-->
Analyze conversation (assistant responses hidden):

${CONVERSATION_HISTORY}

Consider:
1. Is user frustrated? (repeated corrections, negative language)
2. Did user explicitly ask to SEND/CREATE/PUSH a PR to GitHub? (Not just "work on PR" or "prepare changes"—actual submit requests like "create a pr", "push a pr", "open a pr")

Output:
<frustrated>true/false</frustrated>
<pr_request>true/false</pr_request>
