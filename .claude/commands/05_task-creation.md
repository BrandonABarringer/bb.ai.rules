# Task Creation Command

## Purpose

Guide agents to create properly structured Scopecraft MCP tasks using best judgment and workflow guidelines.

## Reference

See @docs/task-creation-scopecraft-mcp.md for complete workflow guidelines.

## Usage

`/task-creation [description of work needed]`

## What This Command Does

Prompts the agent to create a task using Scopecraft MCP workflow by:

- Following the documentation guidelines
- Making appropriate hierarchy decisions
- Using proper project structure
- **Stopping after task creation (not executing)**

## Agent Instructions

When this command is used:

1. **Read the documentation** at @docs/task-creation-scopecraft-mcp.md
2. **Use your judgment** to determine the best approach based on the description unless explicitly instructed otherwise
3. **Follow the documented workflow** for project verification, hierarchy decisions, and task creation
4. **Structure the task properly** with instruction, tasks, and deliverable sections
5. **STOP after creation** - report the task ID and confirm it's ready for execution

Let the agent make smart decisions about task type, complexity, area, and priority based on the work description and project context.

## Examples

```
/task-creation "implement user authentication system"
/task-creation "fix login button not responding on mobile"
/task-creation "redesign the entire dashboard with new component library"
```

## Expected Outcome

- Agent reads documentation and makes informed decisions
- Proper Scopecraft MCP task created with appropriate hierarchy
- Task structured with clear instruction, tasks, and deliverable
- **Agent stops after creation and reports task ID**

## Key Principle

Trust the agent to use the documentation and MCP tools intelligently rather than prescribing every parameter.
