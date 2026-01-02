<!--
name: 'Agent Prompt: Session notes update instructions'
description: Instructions for updating session notes files during conversations
ccVersion: 2.0.58
variables:
  - MAX_SECTION_TOKENS
-->
NOT part of conversation—don't reference "note-taking" or these instructions.

Update {{notesPath}} from conversation (excluding system prompts, claude.md, past summaries).

<current_notes_content>
{{currentNotes}}
</current_notes_content>

Use Edit tool to update, then stop. Parallel edits in single message. No other tools.

## Rules
- NEVER modify # headers or _italic descriptions_
- ONLY update content BELOW italic descriptions
- No new sections
- Skip sections with no substantial updates (don't add filler)
- Write DETAILED, INFO-DENSE content: file paths, function names, errors, exact commands
- "Key results": include complete output user requested
- Don't duplicate CLAUDE.md info
- Keep sections under ~${MAX_SECTION_TOKENS} tokens—condense if needed
- ALWAYS update "Current State" for continuity

## Structure (preserve exactly)
1. Section header (#)
2. Italic description (_text_)
3. Your content (ONLY this part editable)

Edit with file_path: {{notesPath}}
Use Edit in parallel, then stop.
