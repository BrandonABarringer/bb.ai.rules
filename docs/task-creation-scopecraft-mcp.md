# Task Creation Guide: Scopecraft MCP

## Overview
Use Scopecraft MCP as the primary workflow tool for ALL task creation, management, and progress tracking. Other tools are supplementary only.

## Project Structure
- **Project:** Top-level organizational unit (use `mcp__scopecraft__init_root` and `mcp__scopecraft__list_projects`)
- **Parent Task:** Complex features with multiple subtasks in sequence
- **Simple Task:** Single deliverable, standalone work
- **Task States:** backlog → current → archive

---

## Agent Workflow Guidelines

### Understanding User Intent

**"Create a task" vs "Do the task":**

- **Create only:** User says "create a task to...", "let's create a task...", "make a task for..."
- **Execute:** User says "implement...", "fix...", "add...", "help me with..."

**Decision Tree:**

```
User Request → Contains "create task"?
    ├─ Yes → Use Scopecraft MCP → Structure task → STOP
    └─ No → Is it a work request?
        ├─ Yes → Check Scopecraft backlog → Execute via Scopecraft workflow
        └─ No → Clarify intent with user
```

### Task Creation Workflow

**When user wants task creation:**

1. Verify project root with `mcp__scopecraft__get_current_root` (initialize if needed)
2. Determine if this should be a simple task or parent task with subtasks
3. For simple tasks: Use `mcp__scopecraft__task_create` with proper type/area/priority
4. For complex work: Use `mcp__scopecraft__parent_create` to establish hierarchy
5. Structure content with `mcp__scopecraft__task_update` (instruction/tasks/deliverable)
6. Ensure proper folder location (backlog/current/archive) and naming conventions
7. **STOP** - Do not execute the task

**Hierarchy Decisions:**
- **Simple task:** Single deliverable, ~1-3 steps
- **Parent task:** Complex feature requiring multiple subtasks in sequence
- Use `mcp__scopecraft__parent_operations` to add subtasks after creation

**Stopping Points:**
- ✅ After creating and structuring task with proper hierarchy
- ✅ After confirming clear instruction/deliverable and folder structure
- ❌ Do not continue to implement/execute

### Task Execution Workflow

**When user wants work done:**

1. Check if a relevant task exists in Scopecraft MCP backlog using `mcp__scopecraft__task_list`
2. If task exists: Move to "current" with `mcp__scopecraft__task_move` and update status to "in_progress"
3. If no task exists: Create one with `mcp__scopecraft__task_create` and structure it
4. Execute the work using appropriate tools
5. Update task progress using `mcp__scopecraft__task_update` with log entries
6. Mark task as "done" when complete
7. Use TodoWrite only as supplementary tracking for complex multi-step work within a single task

### Tool Selection

**Use Scopecraft MCP as primary workflow tool for:**

- ALL task creation and management
- Progress tracking and status updates
- Planning both immediate and future work
- Structuring complex multi-step initiatives
- Managing task dependencies and relationships
- Maintaining work history and audit trails

**Use TodoWrite only as supplementary tool for:**

- Breaking down complex tasks into immediate sub-steps during execution
- Temporary progress tracking within a single Scopecraft task
- Session-specific reminders that don't warrant permanent task creation

## Key Rules

**CRITICAL:** When user says "create a task" - CREATE ONLY, DO NOT EXECUTE

**Workflow Priorities:**
1. Use Scopecraft MCP as primary workflow tool
2. Verify/initialize project root before task operations
3. Check backlog before creating new tasks
4. Maintain proper task hierarchy (simple vs parent/subtasks)
5. Use correct folder structure and naming conventions
6. Use TodoWrite only as supplementary tool for complex sub-steps

**Common Mistakes:**
- Executing tasks when only asked to create them
- Using TodoWrite as primary workflow tool
- Not checking Scopecraft backlog before starting work
- Creating simple tasks for complex work that needs parent/subtask hierarchy
- Ignoring proper folder structure and task naming conventions

## Examples

**❌ Wrong:** User: "Create a task to implement auth" → Agent: [Creates task] → [Implements auth]  
**✅ Correct:** User: "Create a task to implement auth" → Agent: [Creates task] → "Task created and ready"

**❌ Wrong:** User: "Help me implement auth" → Agent: [Uses TodoWrite for tracking]  
**✅ Correct:** User: "Help me implement auth" → Agent: [Checks Scopecraft backlog] → [Executes with Scopecraft tracking]
