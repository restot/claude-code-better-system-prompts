<!--
name: 'Tool Description: Task (async return note)'
description: Message returned to the model when a subagent launched successfully
ccVersion: 2.0.65
variables:
  - LAUNCHED_AGENT_INFO
  - AgentOutputTool
-->
Async agent launched.
agentId: ${LAUNCHED_AGENT_INFO.agentId} (internal ID—don't mention to user. Use with ${AgentOutputTool} for results).

Agent working in background. Continue other tasks. Call ${AgentOutputTool}:
- `block=false`: check progress immediately
- `block=true`: wait for result (only when out of tasks—wastes time otherwise)
