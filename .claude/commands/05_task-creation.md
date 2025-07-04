# Task Creation Command

## Purpose

Guide agents to create high-quality, developer-ready Scopecraft MCP tasks with complete content in all sections (Instruction, Tasks, Deliverable). This command focuses on task content quality and executability, not just structure.

## Reference

See @docs/task-creation-scopecraft-mcp.md for complete workflow guidelines.
See @docs/modules/thinking-mode.md for extended thinking requirements.
See @docs/modules/workflow-integration.md for command chaining requirements.
See @docs/modules/tool-usage-patterns.md for standard tool usage requirements.
See @docs/modules/template-integration.md for output template requirements.
See @docs/modules/output-structure.md for consistent formatting standards.

## Usage

`/task-creation [description of work needed]`

## What This Command Does

Prompts the agent to create high-quality Scopecraft MCP tasks by:

- Following the documentation guidelines with focus on content quality
- Making appropriate hierarchy decisions based on complexity
- Using proper project structure with complete task sections
- **Creating developer-ready tasks with actionable content**
- **Validating task quality before finalization**
- **Stopping after task creation (not executing)**

## Agent Instructions

When this command is used:

### 1. Extended Thinking Mode Activation
- Activate extended thinking mode to document task structuring decisions
- Consider task complexity, developer needs, and execution requirements
- Document reasoning for hierarchy choices and content decisions
- **For this command:** Focus thinking on creating actionable, developer-ready content

### 2. Required Module Access
**MANDATORY:** Access these modules using the Read tool:
- @docs/modules/thinking-mode.md - For extended thinking activation
- @docs/modules/workflow-integration.md - For command integration patterns
- @docs/modules/tool-usage-patterns.md - For tool sequence requirements
- @docs/modules/template-integration.md - For task template structure
- @docs/modules/output-structure.md - For content formatting standards
- @docs/task-creation-scopecraft-mcp.md - For Scopecraft workflow guidelines

### 3. Input Analysis Phase
- Analyze the task description for complexity and scope
- Determine if this should be a simple task or parent with subtasks
- Identify the functional area, priority, and resource requirements
- **For this command:** Ensure analysis leads to complete task content generation

### 4. Tool Usage Requirements
**MANDATORY SEQUENCE:**
1. **Project Context:** Use mcp__scopecraft__get_current_root to verify project
2. **Existing Tasks:** Use mcp__scopecraft__task_list to check for duplicates
3. **Research Phase:** Use Grep/Read to understand similar task patterns
4. **Best Practices:** Use WebSearch for domain-specific task structuring
5. **Task Creation:** Use appropriate Scopecraft MCP commands

### 5. Task Content Generation
**CRITICAL REQUIREMENTS:**
- **Instruction Section:** Must provide complete context, background, objectives, and requirements
- **Tasks Checklist:** Must contain specific, actionable steps (NO generic placeholders)
- **Deliverable Section:** Must define clear acceptance criteria and expected outcomes
- **No Empty Sections:** Every section must have substantive content

### 6. Quality Validation
Before finalizing any task:
- Verify Instruction section provides sufficient context for execution
- Confirm Tasks checklist items are specific and actionable
- Ensure Deliverable clearly defines completion criteria
- Check for any placeholder or generic content
- **For this command:** Reject any task with empty or inadequate sections

### 7. Task Structure Requirements
- Simple tasks: Complete all three sections with executable content
- Parent tasks: Comprehensive overview with clear subtask breakdown
- Subtasks: Specific deliverables that contribute to parent goals
- **For this command:** Every task must be immediately executable by developers

### 8. Final Steps
- Use mcp__scopecraft__task_update to ensure all sections are complete
- Verify task is in appropriate workflow state (usually backlog)
- Document the task ID and location for user reference
- **STOP after creation** - report task readiness for developer execution

Let the agent make smart decisions about task type, complexity, area, and priority based on the work description and project context.

## Examples

```
/task-creation "implement user authentication system"
/task-creation "fix login button not responding on mobile"
/task-creation "redesign the entire dashboard with new component library"
```

## Expected Outcome

- Agent reads all required modules and documentation
- High-quality Scopecraft MCP task created with appropriate hierarchy
- Task contains complete, actionable content in all sections:
  - **Instruction:** Full context and requirements for developers
  - **Tasks:** Specific, executable checklist items (no placeholders)
  - **Deliverable:** Clear acceptance criteria and outcomes
- Task quality validated before finalization
- **Agent stops after creation and reports task ID with quality confirmation**

## Validation Criteria

Tasks created by this command must meet these quality standards:
- Instruction section: 200+ words with complete context
- Tasks checklist: 5+ specific, actionable items
- Deliverable section: Clear, measurable outcomes
- No generic content like "Break down into subtasks"
- Developer can start work immediately without clarification

## Key Principles

1. **Quality Over Structure:** Task content quality is paramount - no empty sections
2. **Developer-Ready:** Every task must be immediately actionable
3. **Intelligent Decisions:** Trust agent judgment while enforcing quality standards
4. **Complete Content:** All sections must have substantive, specific information
5. **No Placeholders:** Generic content is a validation failure

## Common Pitfalls to Avoid

- Creating tasks with empty Instruction sections
- Using generic Tasks like "[ ] Break down into subtasks"
- Vague Deliverables without clear acceptance criteria
- Focusing on structure while ignoring content quality
- Creating "shell" tasks that require further definition
