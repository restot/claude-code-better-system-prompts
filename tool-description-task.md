<!--
name: 'Tool Description: Task'
description: Tool description for launching specialized sub-agents to handle complex tasks
ccVersion: 2.0.72
variables:
  - TASK_TOOL
  - AGENT_TYPE_REGISTRY_STRING
  - READ_TOOL
  - GLOB_TOOL
  - WRITE_TOOL
  - AGENT_OUTPUT_TOOL
-->
Launch specialized agents for complex, multi-step tasks.

## Available Agents
${AGENT_TYPE_REGISTRY_STRING}

Specify `subagent_type` parameter to select agent.

## When NOT to Use
- Specific file path → use ${READ_TOOL.name} or ${GLOB_TOOL.name}
- Class definition search → use ${GLOB_TOOL.name}
- Code in 2-3 files → use ${READ_TOOL.name}

## Usage
- Include 3-5 word description
- Launch multiple agents concurrently via single message with multiple tool calls
- Agent results not visible to user—summarize for them
- `run_in_background`: retrieve results later with ${TASK_TOOL}
- `resume` parameter: continue from previous agent ID with preserved context
- Agents with "access to current context" see conversation history—use concise prompts
- Tell agent whether to write code or just research
- Use proactively if agent description says so
- Parallel agents: single message with multiple ${WRITE_TOOL.name} calls

## Examples

<example_agent_descriptions>
"code-reviewer": use after writing significant code
"greeting-responder": respond to greetings with joke
</example_agent_description>

<example>
user: "Write a function that checks if a number is prime"
assistant: [writes isPrime function]
<commentary>Significant code written—use code-reviewer agent</commentary>
assistant: Uses ${WRITE_TOOL.name} to launch code-reviewer agent
</example>

<example>
user: "Hello"
<commentary>User greeting—use greeting-responder agent</commentary>
assistant: Uses ${WRITE_TOOL.name} to launch greeting-responder agent
</example>
