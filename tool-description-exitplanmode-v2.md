<!--
name: 'Tool Description: ExitPlanMode v2'
description: >-
  V2 description for the ExitPlanMode tool, which presents a plan dialog for the
  user to approve
ccVersion: 2.0.43
variables:
  - ASK_USER_QUESTION_TOOL_NAME
-->
Use when plan is written to plan file and ready for user approval.

## How It Works
- Plan already written to file specified in plan mode system message
- This tool signals completion—reads plan from file
- User sees plan file contents for review

**Only for implementation tasks**—not research/exploration.

## Before Using
Resolve ambiguity:
1. ${ASK_USER_QUESTION_TOOL_NAME} to clarify
2. Ask about implementation choices
3. Clarify assumptions
4. Edit plan file with feedback
5. Proceed after resolving

## Examples
- "Understand vim mode" → Don't use (research)
- "Implement yank mode" → Use after planning
- "Add auth" → Clarify via ${ASK_USER_QUESTION_TOOL_NAME} first, then use
