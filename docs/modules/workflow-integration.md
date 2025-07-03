# Workflow Integration Module

## Command Chaining Requirements

### Workflow Sequence
Commands must integrate seamlessly in the idea-to-task workflow:
```
brainstorm → feature-proposal → feature-to-prd → feature-planning → task-creation
```

### Integration Pattern
Each command must:
1. **Read previous command output** (if applicable)
2. **Extract required data** from specific sections
3. **Build upon previous findings** rather than starting fresh
4. **Prepare structured output** for next command
5. **Validate integration readiness** before completion

## Data Flow Management

### Previous Command Integration
**For non-initial commands:**
```markdown
### Input Analysis Phase
**[Previous Command] Integration:**
- Use `Read` tool to access previous output: `docs/outputs/sessions/[YYYY-MM-DD]/workflow-[NN]-[topic]/[previous-command]-[topic]-[YYYY-MM-DD].md`
- Extract key insights from [specific sections]
- Identify [relevant data] for current command development
```

### Output Preparation
**For all commands:**
```markdown
### Integration Section Requirements
- **Command Transition:** Ready for `/project:[next-command] [parameters]`
- **Required Inputs:** What next command needs from this output
- **Success Handoff:** Validation criteria for successful transition
```

### Workflow Continuity
- **Topic Consistency:** Use same topic keywords throughout workflow
- **Context Preservation:** Maintain decisions and rationale across commands
- **Data Validation:** Ensure previous outputs are accessible and complete
- **Progress Tracking:** Document workflow advancement and status

## Integration Validation

### Pre-Command Validation
Before executing any non-initial command:
1. **File Existence:** Verify previous command output exists
2. **Template Compliance:** Check previous output follows template
3. **Integration Section:** Confirm previous output has complete Integration section
4. **Data Availability:** Ensure required data is present

### Post-Command Validation
After executing any command:
1. **Output Creation:** Verify file was created successfully
2. **Template Compliance:** Check current output follows template
3. **Integration Preparation:** Confirm Integration section prepares for next command
4. **Workflow Readiness:** Validate successful handoff criteria

## Error Handling Patterns

### Missing Previous Output
```markdown
If previous command output is missing:
1. Document the gap in current command output
2. Proceed with available information and document assumptions
3. Flag missing data requirements clearly
4. Suggest re-running previous command with proper template compliance
```

### Incomplete Integration Data
```markdown
If previous output lacks required integration data:
1. Use available information and document gaps
2. Make reasonable assumptions with clear justification
3. Flag areas needing clarification or additional work
4. Recommend reviewing template compliance for previous command
```

### Template Non-Compliance
```markdown
If previous output doesn't follow template structure:
1. Extract available information using best effort
2. Document format inconsistencies and their impact
3. Proceed with integration using available data
4. Recommend template standardization for future commands
```

## Workflow Orchestration

### Session Management
- **Workflow Directory:** Keep all related outputs in same workflow folder
- **Session Organization:** Group workflows by date in session directories
- **Archive Management:** Move completed workflows to archive folders

### Multi-Workflow Support
- **Sequential Numbering:** workflow-01, workflow-02, etc. for multiple features per day
- **Independent Tracking:** Each workflow maintains its own complete chain
- **Resource Sharing:** Common research can be referenced across workflows

### Command Dependencies
- **Sequential Dependencies:** Each command builds on previous in chain
- **Data Dependencies:** Specific sections provide required inputs
- **Validation Dependencies:** Previous command must be template-compliant
- **Integration Dependencies:** Integration sections must prepare for next step

## Usage in Commands

Reference this module in command instructions with:
```markdown
See @docs/modules/workflow-integration.md for command chaining requirements.
```

## Integration Success Criteria

A successful workflow integration should:
- [ ] Access and utilize previous command outputs effectively
- [ ] Follow designated template structure completely
- [ ] Produce outputs ready for next command consumption
- [ ] Maintain workflow context and decision history
- [ ] Include complete validation and integration sections
- [ ] Provide clear transition instructions for next step

## Practical Implementation

### Directory Creation Process
**For initial workflow commands (like brainstorm):**
1. Use `LS` tool to check `docs/outputs/sessions/[YYYY-MM-DD]/`
2. Parse output to identify existing workflow-XX directories
3. Extract highest number and increment for next workflow
4. Create new directory: `docs/outputs/sessions/[YYYY-MM-DD]/workflow-[NN]-[topic]/`

**Example Implementation:**
```markdown
# Check existing workflows
Use LS tool: docs/outputs/sessions/2024-07-03/
# If workflow-01-auth exists, create workflow-02-[topic]
# If no workflows exist, create workflow-01-[topic]
```

### Topic Keyword Standardization
**Extract topic from `$ARGUMENTS`:**
1. Take first 2-3 meaningful words from arguments
2. Convert to lowercase
3. Replace spaces with hyphens
4. Remove special characters
5. Maintain consistency across entire workflow chain

**Examples:**
- `$ARGUMENTS`: "user authentication system for mobile app" → `user-auth`
- `$ARGUMENTS`: "API performance optimization" → `api-performance`  
- `$ARGUMENTS`: "database migration strategy" → `db-migration`

### Workflow Number Validation
**Before creating new workflow:**
```markdown
1. Use `LS` tool to list session directory
2. Count existing workflow-XX directories
3. Determine next sequential number
4. Validate no conflicts exist
5. Document workflow numbering decision
```

**Conflict Resolution:**
- If directory exists, increment number
- If gap exists (workflow-01, workflow-03), use next sequential (workflow-04)
- Document reasoning in workflow output

## Best Practices

### Command Design
- **Modular Approach:** Design commands to work independently or in sequence
- **Clear Interfaces:** Define exactly what each command provides and requires
- **Error Resilience:** Handle missing or incomplete previous outputs gracefully
- **Progress Tracking:** Document advancement through workflow clearly

### Integration Maintenance
- **Template Updates:** Ensure integration sections evolve with command changes
- **Validation Testing:** Test integration paths regularly
- **Documentation Sync:** Keep integration guide updated with command changes
- **Error Pattern Analysis:** Learn from integration failures to improve design