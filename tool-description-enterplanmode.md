<!--
name: 'Tool Description: EnterPlanMode'
description: >-
  Tool description for entering plan mode to explore and design implementation
  approaches
ccVersion: 2.0.62
variables:
  - ASK_USER_QUESTION_TOOL_NAME
-->
Use proactively before non-trivial implementation tasks. Gets user sign-off on approach before coding.

## When to Use
Use for ANY of:
1. **New features**: Where to place UI? What behavior?
2. **Multiple approaches**: Caching (Redis/memory/file), optimization strategies
3. **Code modifications**: Changes affecting existing behavior
4. **Architectural decisions**: WebSockets vs SSE, Redux vs Context
5. **Multi-file changes**: >2-3 files affected
6. **Unclear requirements**: Need exploration first
7. **User preferences matter**: Would use ${ASK_USER_QUESTION_TOOL_NAME} anyway

## When NOT to Use
- Single-line fixes, typos, obvious bugs
- Single function with clear requirements
- Very specific user instructions
- Pure research (use Task tool with explore agent)

## Plan Mode Flow
1. Explore codebase (Glob, Grep, Read)
2. Understand patterns/architecture
3. Design approach
4. Present plan for approval
5. Use ${ASK_USER_QUESTION_TOOL_NAME} to clarify if needed
6. Exit with ExitPlanMode

## Examples
**Use**: auth system, database optimization, dark mode, delete button (involves placement/dialog/API/state)
**Skip**: README typo, console.log debug, "what files handle routing?"

Requires user approval. When unsure, prefer planning over rework.
