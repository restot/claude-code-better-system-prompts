<!--
name: 'Tool Description: TaskUpdate'
description: 'Description for the TaskUpdate tool, which updates Claude''s task list'
ccVersion: 2.0.60
-->
Update tasks in task list.

## When to Use
- **Mark resolved**: Work complete, no longer needed, superseded. ALWAYS mark assigned tasks resolved when done.
- **Update details**: Requirements changed, add comments, establish dependencies.

## Fields
- **status**: 'resolved' / 'open'
- **subject/description**: Change title/description
- **addComment**: `{author, content}` for progress. Use `CLAUDE_CODE_AGENT_ID` as author.
- **addReferences**: Link related tasks (bidirectional)
- **addBlocks/addBlockedBy**: Dependency ordering

## Task Ownership
**Claim task before updating.** Only update assigned tasks (team leads can update any).

Claim via TeammateTool:
- Lead: `assignTask` to assign
- Teammate: `claimTask` to self-claim

## Examples
```json
{"taskId": "1", "status": "resolved"}
{"taskId": "2", "addComment": {"author": "agent-id", "content": "Found root cause"}}
{"taskId": "3", "status": "resolved", "addComment": {"author": "agent-id", "content": "Done"}}
```
