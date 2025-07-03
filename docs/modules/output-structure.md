# Output Structure Module

## Standardized Output Organization

### Directory Structure Requirements
All command outputs must use the scalable directory structure:

```
docs/outputs/sessions/[YYYY-MM-DD]/workflow-[NN]-[topic]/[command-name]-[topic-keyword]-[YYYY-MM-DD].md
```

### Directory Creation Instructions
1. **Session Directory:** `docs/outputs/sessions/[YYYY-MM-DD]/`
2. **Workflow Directory:** `workflow-[NN]-[topic]/` (where NN is sequential: 01, 02, 03...)
3. **Full Path Example:** `docs/outputs/sessions/2024-07-03/workflow-01-user-auth/`

### File Naming Convention
**Pattern:** `[command-name]-[topic-keyword]-[YYYY-MM-DD].md`

**Examples:**
- `brainstorm-user-auth-2024-07-03.md`
- `feature-proposal-user-auth-2024-07-03.md`
- `feature-prd-mobile-ui-2024-07-04.md`

### Topic Keywords Guidelines
- Use 2-3 hyphenated words maximum
- Focus on main feature or problem area
- Keep consistent across entire workflow
- Common examples: `user-auth`, `api-performance`, `mobile-ui`, `data-sync`

### Output Creation Instructions
```markdown
1. Create workflow directory if first command in sequence
2. Use `Write` tool with full path
3. Follow designated template structure
4. Complete validation checklist before finishing
5. Prepare integration section for next command
```

### Archive Management
- **Active Sessions:** Keep in `sessions/[YYYY-MM-DD]/`
- **Completed Workflows:** Move to `archives/[YYYY-MM]/`
- **Archive Trigger:** When workflow reaches task-creation completion

## Structured Presentation Format

### Standard Output Sections
All command outputs should follow this structure:

```markdown
## Context
[Problem understanding and scope]

## Research
[Validation findings from multiple sources]

## Analysis
[Evidence-based conclusions and patterns]

## Recommendations
[Next steps with supporting rationale]

## Integration
[Preparation for next command in workflow]
```

### Template Integration
- Reference specific template: `@docs/templates/[command-name]-output-template.md`
- Use `Read` tool to access template structure
- Follow template format exactly
- Complete all template validation checklists

## Workflow Integration

### Command Chaining
- Each command reads previous command output from same workflow directory
- Use consistent topic keywords across entire workflow
- Maintain context and decision rationale throughout pipeline
- Reference specific sections from previous outputs

### Integration Validation
- Verify previous command output exists before proceeding
- Validate template compliance of previous outputs
- Check Integration section completeness
- Confirm required data is available for current command

## Usage in Commands

Reference this module in command instructions with:
```markdown
See @docs/modules/output-structure.md for output organization requirements.
```

## Error Handling

### Missing Previous Output
1. Document the gap in current command output
2. Proceed with available information
3. Flag missing data requirements
4. Suggest re-running previous command

### Directory Creation
1. Create directories if they don't exist
2. Use consistent naming conventions
3. Maintain scalable structure
4. Document directory creation in output