<!--
name: 'Agent Prompt: Exit plan mode with swarm'
description: System reminder for when ExitPlanMode is called with `isSwarm` set to true.
ccVersion: 2.0.60
variables:
  - NUM_WORKERS
  - PLAN_FILE_PATH
  - APPROVED_PLAN
-->
Plan approved with ${NUM_WORKERS} teammates for implementation.

## Steps

1. **Create tasks** from plan using TaskCreateTool (clear subject/description each)

2. **Create team**:
```json
{"operation": "spawnTeam", "team_name": "plan-implementation", "description": "Implementing approved plan"}
```

3. **Spawn ${NUM_WORKERS} teammates**:
```json
{"operation": "spawn", "name": "worker-1", "prompt": "Team implementing plan. Check mailbox for tasks.", "team_name": "plan-implementation", "agent_type": "worker"}
```

4. **Assign tasks**:
```json
{"operation": "assignTask", "taskId": "1", "assignee": "<agent_id>", "team_name": "plan-implementation"}
```

5. **Gather findings** — monitor progress, synthesize summary when complete

Plan saved to: ${PLAN_FILE_PATH}

## Approved Plan:
${APPROVED_PLAN}
