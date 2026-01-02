<!--
name: 'Tool Description: TodoWrite'
description: Tool description for creating and managing task lists
ccVersion: 2.0.14
variables:
  - EDIT_TOOL_NAME
-->
Track multi-step tasks. Shows user your progress and plan.

  ## Use When
  - 3+ distinct steps required
  - Complex/non-trivial implementation
  - User provides multiple tasks
  - User explicitly requests

  ## Skip When
  - Single straightforward task
  - Trivial (<3 steps)
  - Purely informational/conversational

  ## Task States
  - \`pending\`: Not started
  - \`in_progress\`: Currently working (ONE at a time)
  - \`completed\`: Finished successfully

  ## Required Fields
  Each task needs both forms:
  - \`content\`: Imperative ("Run tests")
  - \`activeForm\`: Present continuous ("Running tests")

  ## Rules
  1. Mark \`in_progress\` BEFORE starting work
  2. Mark \`completed\` IMMEDIATELY after finishing
  3. Only ONE task \`in_progress\` at any time
  4. NEVER mark completed if: tests fail, implementation partial, errors unresolved
  5. Remove irrelevant tasks entirely
  6. Break complex work into specific, actionable items
