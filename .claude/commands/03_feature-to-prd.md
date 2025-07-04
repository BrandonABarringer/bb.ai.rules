# Feature to PRD Command

## Purpose

Transform feature proposals into comprehensive Product Requirements Documents (PRDs) with stakeholder analysis, business context, and detailed specifications ready for engineering planning.

## Usage

`/project:feature-to-prd`
(Automatically uses feature proposal from previous workflow step)

Optional override:
`/project:feature-to-prd [specific feature proposal to develop instead]`

## Instructions

When this command is used, follow this structured workflow:

### 1. Enable Extended Thinking Mode
See @docs/modules/thinking-mode.md for extended thinking mode requirements.
**For this command:** Use Read tool to access module and document activation in thinking section.

### 2. Input Analysis Phase
See @docs/modules/workflow-integration.md for command chaining requirements.
See @docs/modules/tool-usage-patterns.md for standard tool usage requirements.
**For this command:** Use Read tool to access modules and document guidance in thinking section.

**Feature Proposal Integration (MANDATORY):**
- **Use Read tool for previous output integration:** Access previous feature-proposal output from same workflow directory
- Extract technical requirements and feasibility assessment with specific quotes/references
- Identify user stories and acceptance criteria with exact text extraction
- Document success metrics and validation criteria from proposal
- Document the file path and specific sections referenced

**Stakeholder Analysis (MANDATORY TOOL SEQUENCE):**
- **Use Grep tool for stakeholder discovery:** Search for existing user personas, stakeholder docs, business requirements (minimum 1 search, document findings)
- **Use Glob tool for documentation discovery:** Identify business docs, user research, market analysis files (minimum 1 search, document findings)
- **Use Read tool for context analysis:** Analyze discovered stakeholder documentation for business context (minimum 1 file, document findings)
- **Use WebSearch tool for market validation:** Research market positioning, competitive analysis, industry standards (minimum 1 search, document findings)
- Document each tool use and its contribution to stakeholder understanding

### 3. Business Context Development
- Define clear business objectives and success criteria
- Identify target user segments and stakeholder groups
- Establish market positioning and competitive differentiators
- Outline business impact metrics and validation methods

### 4. Technical Specification Refinement
- Expand technical requirements from feature proposal
- Define system architecture and integration points
- Specify performance requirements and constraints
- Identify security, compliance, and accessibility requirements

### 5. Stakeholder Communication Planning
- Create stakeholder-specific communication strategies
- Define review cycles and approval processes
- Establish feedback collection and iteration methods
- Plan for cross-functional collaboration requirements

### 6. Structured PRD Presentation
See @docs/modules/template-integration.md for template usage requirements.
See @docs/modules/output-structure.md for output organization requirements.
**For this command:** Use Read tool to access modules and template, document compliance in thinking section.

**MANDATORY TEMPLATE COMPLIANCE:**
- Follow PRD template structure exactly with all required sections
- Replace all bracketed placeholders with actual content
- Complete stakeholder matrix with roles and responsibilities
- Include comprehensive validation checklist completion at end of output

### 7. Workflow Integration & Validation
See @docs/modules/workflow-integration.md for command chaining requirements.
**For this command:** Use Read tool to access module and document integration preparation.

**MANDATORY VALIDATION PROCESS:**
- Complete template validation checklist before finishing
- Verify all business objectives have measurable success criteria
- Confirm technical specifications are implementation-ready
- Ensure stakeholder responsibilities are clearly defined
- Validate Integration section prepares for `/project:feature-planning`

This is the third command in the workflow sequence. Ensure Integration section prepares for `/project:feature-planning` command.

### 8. Final Validation & Output
**CRITICAL REQUIREMENTS:**
- Include completed validation checklist from template at end of output
- Use `Write` tool to create file in correct workflow directory
- Maintain topic consistency with previous feature-proposal command
- Ensure file naming follows convention: `feature-to-prd-[topic]-[YYYY-MM-DD].md`

## Expected Outcome

- Comprehensive PRD with clear business objectives and context
- Detailed technical specifications ready for engineering planning
- Stakeholder analysis with defined roles and responsibilities
- Success metrics and validation criteria for all requirements
- Clear next steps for feature planning and implementation
- **CRITICAL:** Completed validation checklist included in output
- **CRITICAL:** All module access documented in thinking mode section
- **CRITICAL:** All tool usage documented with contribution analysis

## Arguments

**Default behavior:** Command automatically extracts feature proposal from previous workflow step in same directory.

**Override behavior:** Use `$ARGUMENTS` to specify a different feature proposal or description for PRD development if you want to develop something other than the workflow's current feature proposal.

## Example Usage

```
# Automatic mode (uses workflow feature proposal)
/project:feature-to-prd

# Override mode (develop specific proposal)
/project:feature-to-prd user authentication system with enterprise SSO
/project:feature-to-prd real-time collaboration dashboard with analytics
/project:feature-to-prd mobile performance monitoring with AI insights
```

## Integration Notes

This command is the third step in the idea-to-task workflow:
`brainstorm ’ feature-proposal ’ feature-to-prd ’ feature-planning ’ task-creation`

Results from this command should provide comprehensive PRD documentation for detailed project planning and engineering implementation phases.