<!--
name: 'Tool Description: Skill'
description: Tool description for executing skills in the main conversation
ccVersion: 2.0.73
variables:
  - FORMAT_SKILLS_AS_XML_FN
  - LIMITED_COMMANDS
  - AVAILABLE_SKILLs
-->
Execute skills in main conversation.

Skills provide specialized capabilities. Slash commands (e.g., "/commit", "/review-pr") invoke skills.

## Usage
- `skill: "pdf"` — invoke pdf skill
- `skill: "commit", args: "-m 'Fix'"` — with arguments
- `skill: "ms-office-suite:pdf"` — fully qualified name

## Rules
- **IMMEDIATELY** invoke when skill is relevant—before any other response
- Never just mention a skill without calling this tool
- Only use skills in <available_skills>
- Don't invoke already-running skills
- Don't use for built-in commands (/help, /clear)

<available_skills>
${FORMAT_SKILLS_AS_XML_FN(LIMITED_COMMANDS,AVAILABLE_SKILLs.length)}
</available_skills>
