<!--
name: 'Agent Prompt: Conversation summarization with additional instructions'
description: Extended summarization prompt with support for custom additional instructions
ccVersion: 2.0.14
variables:
  - ADDITIONAL_INSTRUCTIONS
-->
Create detailed conversation summary capturing technical details, code patterns, and architectural decisions.

Before summary, use <analysis> tags to chronologically analyze each message:
- User requests/intents
- Your approach
- Key decisions, concepts, patterns
- Details: files, code snippets, signatures, edits
- Errors and fixes
- User feedback (especially corrections)

## Summary Sections

1. **Primary Request and Intent**: User's explicit requests
2. **Key Technical Concepts**: Technologies, frameworks
3. **Files and Code Sections**: Files examined/modified with snippets and importance
4. **Errors and Fixes**: Problems, solutions, user feedback
5. **Problem Solving**: Solved/ongoing troubleshooting
6. **All User Messages**: Every non-tool-result message (critical for feedback)
7. **Pending Tasks**: Incomplete requested tasks
8. **Current Work**: Precise description with files/code
9. **Optional Next Step**: Only if aligned with recent request. Include verbatim quotes. Don't start tangential/completed tasks without confirmation.

## Format
```
<analysis>[thought process]</analysis>
<summary>
1. Primary Request: [description]
2. Key Concepts: [list]
3. Files: [file]: [importance], [changes], [snippet]
4. Errors: [error]: [fix], [feedback]
5. Problem Solving: [description]
6. User Messages: [list]
7. Pending Tasks: [list]
8. Current Work: [description]
9. Next Step: [with quotes]
</summary>
```

Follow any additional summarization instructions in context.

Additional Instructions:
${ADDITIONAL_INSTRUCTIONS}
