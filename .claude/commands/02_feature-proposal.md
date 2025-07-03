# Feature Proposal Command

## Purpose

Transform brainstormed ideas into structured feature proposals with detailed requirements and feasibility analysis.

## Usage

`/project:feature-proposal`
(Automatically uses primary recommendation from previous brainstorm)

Optional override:
`/project:feature-proposal [specific idea to develop instead]`

## Instructions

When this command is used, follow this structured workflow:

### 1. Enable Extended Thinking Mode
See @docs/modules/thinking-mode.md for extended thinking mode requirements.
**For this command:** Use Read tool to access module and document activation in thinking section.

### 2. Input Analysis Phase
See @docs/modules/workflow-integration.md for command chaining requirements.
See @docs/modules/tool-usage-patterns.md for standard tool usage requirements.
**For this command:** Use Read tool to access modules and document guidance in thinking section.

**Brainstorm Integration (MANDATORY):**
- **Use Read tool for previous output integration:** Access previous brainstorm output from same workflow directory
- Extract key insights from Research and Analysis sections with specific quotes/references
- Identify selected ideas from Recommendations section with exact text extraction
- Document the file path and specific sections referenced

**Feature Scope Definition (MANDATORY TOOL SEQUENCE):**
- **Use Grep tool for codebase analysis:** Search for existing feature discovery in codebase (minimum 1 search, document findings)
- **Use Glob tool for file discovery:** Identify related file patterns (minimum 1 search, document findings)  
- **Use Read tool for architecture analysis:** Analyze discovered files for architectural patterns (minimum 1 file, document findings)
- **Use WebSearch tool for external validation:** Research implementation pattern validation (minimum 1 search, document findings)
- Document each tool use and its contribution to feasibility assessment

### 3. Requirement Structuring Process
- Define clear user stories and acceptance criteria
- Identify technical requirements and dependencies
- Establish success metrics and validation criteria
- Outline resource requirements and timeline estimates

### 4. Feasibility Assessment
- Evaluate technical complexity against current architecture
- Assess resource requirements (development, design, testing)
- Identify potential risks and mitigation strategies
- Compare against alternative approaches from brainstorm phase

### 5. Structured Presentation
See @docs/modules/template-integration.md for template usage requirements.
See @docs/modules/output-structure.md for output organization requirements.
**For this command:** Use Read tool to access modules and template, document compliance in thinking section.

**MANDATORY TEMPLATE COMPLIANCE:**
- Follow template structure exactly with all required sections
- Replace all bracketed placeholders with actual content
- Complete feasibility matrix with scores and justifications
- Include validation checklist completion at end of output

### 6. Workflow Integration & Validation
See @docs/modules/workflow-integration.md for command chaining requirements.
**For this command:** Use Read tool to access module and document integration preparation.

**MANDATORY VALIDATION PROCESS:**
- Complete template validation checklist before finishing
- Verify all user stories have acceptance criteria
- Confirm technical feasibility is thoroughly assessed
- Ensure risk mitigation strategies are included
- Validate Integration section prepares for `/project:feature-to-prd`

This is the second command in the workflow sequence. Ensure Integration section prepares for `/project:feature-to-prd` command.

### 7. Final Validation & Output
**CRITICAL REQUIREMENTS:**
- Include completed validation checklist from template at end of output
- Use `Write` tool to create file in correct workflow directory
- Maintain topic consistency with previous brainstorm command
- Ensure file naming follows convention: `feature-proposal-[topic]-[YYYY-MM-DD].md`

## Expected Outcome

- Comprehensive feature proposal with clear requirements
- Technical feasibility assessment with supporting analysis  
- Structured requirements ready for PRD development
- Risk assessment and mitigation strategies
- Clear next steps for project planning phase
- **CRITICAL:** Completed validation checklist included in output
- **CRITICAL:** All module access documented in thinking mode section
- **CRITICAL:** All tool usage documented with contribution analysis

## Arguments

**Default behavior:** Command automatically extracts primary recommendation from previous brainstorm output in same workflow directory.

**Override behavior:** Use `$ARGUMENTS` to specify a different idea or feature description for proposal development if you want to develop something other than the brainstorm's primary recommendation.

## Example Usage

```
# Automatic mode (uses brainstorm primary recommendation)
/project:feature-proposal

# Override mode (develop specific idea)
/project:feature-proposal user authentication system with social login
/project:feature-proposal real-time collaboration features for document editing
/project:feature-proposal mobile app performance optimization dashboard
```

## Integration Notes

This command is the second step in the idea-to-task workflow:
`brainstorm � feature-proposal � feature-to-prd � feature-planning � task-creation`

Results from this command should provide structured input for PRD development and project planning phases.