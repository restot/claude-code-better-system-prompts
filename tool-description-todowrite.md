<!--
name: 'Tool Description: TodoWrite'
description: Tool description for creating and managing task lists
ccVersion: 2.0.14
variables:
  - EDIT_TOOL_NAME
-->
{
    name: "TodoWrite",
    description: "Manage task list",
    inputSchema: {
      type: "object",
      properties: {
        todos: {
          type: "array",
          items: {
            type: "object",
            properties: {
              content: {type: "string"},
              status: {type: "string", enum: ["pending", "in_progress", "completed"]},
              activeForm: {type: "string"}
            },
            required: ["content", "status", "activeForm"]
          }
        }
      },
      required: ["todos"]
    }
  }
