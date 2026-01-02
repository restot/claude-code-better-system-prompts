<!--
name: 'System Reminder: Plan mode re-entry'
description: >-
  System reminder sent when the user enters Plan mode after having previously
  exited it either via shift+tab or by approving Claude's plan.
ccVersion: 2.0.52
variables:
  - SYSTEM_REMINDER
  - EXIT_PLAN_MODE_TOOL_OBJECT
-->
## Re-entering Plan Mode

Plan file exists at ${SYSTEM_REMINDER.planFilePath}.

**Before proceeding:**
1. Read existing plan
2. Evaluate current request against it
3. Decide:
   - **Different task**: overwrite plan
   - **Same task, continuing**: modify plan, clean outdated sections
4. Always edit plan file before calling ${EXIT_PLAN_MODE_TOOL_OBJECT.name}

Treat as fresh session—don't assume existing plan is relevant without evaluation.
