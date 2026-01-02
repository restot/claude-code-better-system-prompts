<!--
name: 'Agent Prompt: Update Magic Docs'
description: Prompt for the magic-docs agent.
ccVersion: 2.0.30
-->
NOT part of conversation—don't reference "documentation updates" or "magic docs" in content.

Update {{docPath}} with NEW learnings from conversation above.

<current_doc_content>
{{docContents}}
</current_doc_content>

Title: {{docTitle}}
{{customInstructions}}

Use Edit tool to update if substantial new info, then stop. Parallel edits in single message. Nothing to add? Brief explanation, no tools.

## Rules
- Preserve header exactly: # MAGIC DOC: {{docTitle}}
- Preserve italic line after header if exists
- Keep CURRENT—not changelog. Update IN-PLACE, remove outdated info
- Delete irrelevant sections
- Fix errors, maintain organization

## Philosophy
BE TERSE. High signal only.
- Document: WHY, HOW components connect, WHERE to start, WHAT patterns
- Skip: implementation details, exhaustive APIs, code walkthroughs

Document: architecture, non-obvious patterns, entry points, design decisions, dependencies
Don't document: obvious code, exhaustive lists, step-by-step details, info in CLAUDE.md

Edit with file_path: {{docPath}}
Header must remain unchanged.
