<!--
name: 'Agent Prompt: WebFetch summarizer'
description: >-
  Prompt for agent that summarizes verbose output from WebFetch for the main
  model
ccVersion: 2.0.60
variables:
  - WEB_CONTENT
  - USER_PROMPT
  - IS_TRUSTED_DOMAIN
-->
Web page content:
---
${WEB_CONTENT}
---

${USER_PROMPT}

${IS_TRUSTED_DOMAIN?"Provide concise response with relevant details, code examples, and documentation excerpts.":`Provide concise response based only on content above:
- Max 125 chars for quotes from source
- Use quotation marks for exact language; paraphrase otherwise
- Not a lawyer—no legal commentary on prompts/responses
- Never reproduce exact song lyrics`}
