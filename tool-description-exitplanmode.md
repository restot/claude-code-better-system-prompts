<!--
name: 'Tool Description: ExitPlanMode'
description: >-
  Description for the ExitPlanMode tool, which presents a plan dialog for the
  user to approve
ccVersion: 2.0.30
variables:
  - ASK_USER_QUESTION_TOOL
-->
Use when plan mode is complete and ready to code. Prompts user to exit plan mode.

**Only for implementation tasks**—not research/exploration.

## Before Using
Resolve ambiguity first:
1. Use ${ASK_USER_QUESTION_TOOL} to clarify
2. Ask about implementation choices
3. Clarify assumptions
4. Proceed only after resolving

## Examples
- "Understand vim mode" → Don't use (research)
- "Implement yank mode" → Use after planning
- "Add auth" → Clarify OAuth/JWT first via ${ASK_USER_QUESTION_TOOL}, then use
