# Command Integration Guide

## Overview

This guide documents how slash commands in the idea-to-task workflow pass data between each other, ensuring seamless integration and reproducible outcomes.

## Workflow Integration Chain

```
/project:brainstorm → /project:feature-proposal → /project:feature-to-prd → /project:feature-planning → /project:task-creation
```

## Command Data Flow

### 1. Brainstorm → Feature Proposal

**Input Transfer:**
- **Source:** Brainstorm output file (e.g., `docs/outputs/sessions/2024-07-03/workflow-01-user-auth/brainstorm-user-auth-2024-07-03.md`)
- **Consumer:** Feature proposal command via `Read` tool
- **Data Used:** Selected ideas, research validation, feasibility assessment

**Integration Process:**
1. Feature proposal command reads brainstorm output file
2. Extracts selected ideas from Recommendations section
3. Leverages research findings to support technical feasibility
4. Uses comparative analysis for alternative approaches

**Template References:**
- **Output Template:** `@docs/templates/brainstorm-output-template.md`
- **Integration Section:** Provides "Selected Ideas" and "Key Requirements"

### 2. Feature Proposal → Feature to PRD

**Input Transfer:**
- **Source:** Feature proposal output file (e.g., `docs/outputs/sessions/2024-07-03/workflow-01-user-auth/feature-proposal-user-auth-2024-07-03.md`)
- **Consumer:** Feature to PRD command via `Read` tool
- **Data Used:** Requirements breakdown, feasibility matrix, stakeholder review needs

**Integration Process:**
1. Feature to PRD command reads feature proposal output
2. Converts requirements into formal PRD structure
3. Uses feasibility matrix for technical specifications
4. Leverages stakeholder review section for approval workflow

**Template References:**
- **Output Template:** `@docs/templates/feature-proposal-output-template.md`
- **Integration Section:** Provides "PRD Preparation" and "Technical Specifications"

## Output Organization Structure

### Scalable Directory Structure
```
docs/outputs/
├── sessions/
│   ├── YYYY-MM-DD/
│   │   ├── workflow-01-[topic]/
│   │   │   ├── brainstorm-[topic]-YYYY-MM-DD.md
│   │   │   ├── feature-proposal-[topic]-YYYY-MM-DD.md
│   │   │   ├── feature-prd-[topic]-YYYY-MM-DD.md
│   │   │   ├── feature-planning-[topic]-YYYY-MM-DD.md
│   │   │   └── task-creation-[topic]-YYYY-MM-DD.md
│   │   └── workflow-02-[topic]/
│   │       └── [additional workflows for same day]
│   └── archives/
│       └── YYYY-MM/
│           └── [completed workflows]
```

### File Naming Conventions

**Standardized Pattern:**
```
[command-name]-[topic-keyword]-[YYYY-MM-DD].md
```

**Full Path Pattern:**
```
docs/outputs/sessions/[YYYY-MM-DD]/workflow-[NN]-[topic]/[command-name]-[topic-keyword]-[YYYY-MM-DD].md
```

### Examples
- `docs/outputs/sessions/2024-07-03/workflow-01-user-auth/brainstorm-user-auth-2024-07-03.md`
- `docs/outputs/sessions/2024-07-03/workflow-01-user-auth/feature-proposal-user-auth-2024-07-03.md`
- `docs/outputs/sessions/2024-07-04/workflow-01-mobile-ui/brainstorm-mobile-ui-2024-07-04.md`

### Topic Keywords
- Use 2-3 hyphenated words maximum
- Focus on the main feature or problem area
- Keep consistent across the entire workflow
- Examples: `user-auth`, `api-performance`, `mobile-ui`

### Workflow Organization
- **Sessions**: Date-based folders for all work done on a specific day
- **Workflows**: Sequential numbering for multiple feature workflows per session
- **Archives**: Monthly folders for completed workflows
- **Scalability**: Supports unlimited workflows and sessions

## Command Integration Requirements

### Template Compliance
Each command must:
- [ ] Use the designated output template from `@docs/templates/`
- [ ] Include complete Integration section
- [ ] Reference previous command outputs when applicable
- [ ] Provide structured data for next command

### File Output Requirements
Each command must:
- [ ] Save output using `Write` tool with standardized filename
- [ ] Include validation checklist completion
- [ ] Ensure all template sections are populated
- [ ] Provide clear transition instructions

### Cross-Reference Validation
Commands must:
- [ ] Use `Read` tool to access previous command outputs
- [ ] Validate data consistency across workflow steps
- [ ] Reference specific sections from previous outputs
- [ ] Maintain context and decision rationale

## Integration Validation

### Pre-Command Validation
Before executing any command (except brainstorm):
1. Verify previous command output file exists
2. Validate template compliance of previous output
3. Check Integration section completeness
4. Confirm required data is available

### Post-Command Validation
After executing any command:
1. Verify output file was created successfully
2. Validate template structure compliance
3. Check Integration section preparation for next command
4. Confirm validation checklist is complete

## Error Handling

### Missing Previous Output
If previous command output is missing:
1. Document the gap in current command output
2. Proceed with available information
3. Flag missing data requirements
4. Suggest re-running previous command

### Incomplete Integration Data
If previous output lacks required integration data:
1. Use available information and document gaps
2. Make reasonable assumptions with justification
3. Flag areas needing clarification
4. Suggest template compliance review

### Template Non-Compliance
If previous output doesn't follow template:
1. Extract available information
2. Document format inconsistencies
3. Proceed with best effort integration
4. Recommend template standardization

## Best Practices

### Command Execution
- Always reference previous command outputs when available
- Use `@docs/templates/[template-name]` for output structure
- Include file output instructions in command completion
- Validate integration data before proceeding

### Template Usage
- Follow template structure exactly
- Replace all bracketed placeholders with actual content
- Maintain consistent formatting and style
- Include all required sections and checklists

### Data Consistency
- Use consistent terminology across workflow
- Maintain decision rationale throughout pipeline
- Reference specific sections from previous outputs
- Preserve context and assumptions

## Troubleshooting

### Common Integration Issues
1. **Missing Files:** Check filename spelling and date format
2. **Template Mismatch:** Verify template version and structure
3. **Data Gaps:** Review Integration section completeness
4. **Context Loss:** Ensure previous command references are included

### Resolution Steps
1. Identify the specific integration failure point
2. Review template compliance of previous commands
3. Re-execute commands with proper template usage
4. Validate data flow through each workflow step

## Integration Success Criteria

A successful command integration should:
- [ ] Access and use previous command outputs
- [ ] Follow designated template structure
- [ ] Produce output ready for next command
- [ ] Maintain workflow context and decisions
- [ ] Include complete validation checklist
- [ ] Provide clear transition instructions