# Feature Planning Command

## Purpose

Transform comprehensive PRDs into detailed engineering project plans with task breakdown, resource allocation, timeline planning, and implementation strategy ready for engineering execution.

## Usage

`/project:feature-planning`
(Automatically uses PRD from previous workflow step)

Optional override:
`/project:feature-planning [specific PRD or feature description to plan instead]`

## Instructions

When this command is used, follow this structured workflow:

### 1. Enable Extended Thinking Mode
See @docs/modules/thinking-mode.md for extended thinking mode requirements.
**For this command:** Use Read tool to access module and document activation in thinking section.

### 2. Input Analysis Phase
See @docs/modules/workflow-integration.md for command chaining requirements.
See @docs/modules/tool-usage-patterns.md for standard tool usage requirements.
**For this command:** Use Read tool to access modules and document guidance in thinking section.

**PRD Integration (MANDATORY):**
- **Use Read tool for previous output integration:** Access previous feature-to-prd output from same workflow directory
- Extract technical specifications and architecture requirements with specific quotes/references
- Identify implementation phases and resource requirements with exact text extraction
- Document success criteria and validation methods from PRD
- Document the file path and specific sections referenced

**Engineering Planning Research (MANDATORY TOOL SEQUENCE):**
- **Use Grep tool for project planning discovery:** Search for existing project templates, planning docs, engineering processes (minimum 1 search, document findings)
- **Use Glob tool for development methodology discovery:** Identify agile templates, sprint planning docs, project management files (minimum 1 search, document findings)
- **Use Read tool for methodology analysis:** Analyze discovered project planning documentation for engineering context (minimum 1 file, document findings)
- **Use WebSearch tool for project management validation:** Research project planning best practices, engineering methodologies, timeline estimation (minimum 1 search, document findings)
- Document each tool use and its contribution to project planning understanding

### 3. Project Scope and Architecture Planning
- Define detailed project scope and deliverable breakdown
- Establish technical architecture and implementation approach
- Identify system integrations and dependency requirements
- Outline development environment and infrastructure needs

### 4. Engineering Task Breakdown Structure
- Create comprehensive work breakdown structure (WBS)
- Define specific engineering tasks with clear acceptance criteria
- Establish task dependencies and critical path analysis
- Specify technical requirements for each development phase

### 5. Resource Allocation and Timeline Planning
- Determine required engineering roles and skill sets
- Estimate effort and duration for each development phase
- Create detailed project timeline with milestones and deliverables
- Plan for code reviews, testing, and quality assurance activities

### 6. Risk Management and Mitigation Planning
- Identify technical risks and implementation challenges
- Define risk mitigation strategies and contingency plans
- Establish monitoring and alerting for project health
- Plan for scope changes and requirement evolution

### 7. Structured Project Plan Presentation
See @docs/modules/template-integration.md for template usage requirements.
See @docs/modules/output-structure.md for output organization requirements.
**For this command:** Use Read tool to access modules and template, document compliance in thinking section.

**MANDATORY TEMPLATE COMPLIANCE:**
- Follow project planning template structure exactly with all required sections
- Replace all bracketed placeholders with actual content
- Complete resource allocation matrix with roles and responsibilities
- Include comprehensive validation checklist completion at end of output

### 8. Workflow Integration & Validation
See @docs/modules/workflow-integration.md for command chaining requirements.
**For this command:** Use Read tool to access module and document integration preparation.

**MANDATORY VALIDATION PROCESS:**
- Complete template validation checklist before finishing
- Verify all project phases have clear deliverables and acceptance criteria
- Confirm resource allocation is realistic and achievable
- Ensure timeline includes adequate buffer for testing and iteration
- Validate Integration section prepares for `/project:task-creation`

This is the fourth command in the workflow sequence. Ensure Integration section prepares for `/project:task-creation` command.

### 9. Final Validation & Output
**CRITICAL REQUIREMENTS:**
- Include completed validation checklist from template at end of output
- Use `Write` tool to create file in correct workflow directory
- Maintain topic consistency with previous feature-to-prd command
- Ensure file naming follows convention: `feature-planning-[topic]-[YYYY-MM-DD].md`

## Expected Outcome

- Comprehensive project plan with detailed engineering task breakdown
- Resource allocation matrix with specific roles and skill requirements
- Detailed timeline with milestones, dependencies, and critical path analysis
- Risk management framework with mitigation strategies and contingency plans
- Quality assurance plan with testing strategy and review processes
- Clear next steps for engineering task creation and sprint planning
- **CRITICAL:** Completed validation checklist included in output
- **CRITICAL:** All module access documented in thinking mode section
- **CRITICAL:** All tool usage documented with contribution analysis

## Arguments

**Default behavior:** Command automatically extracts PRD from previous workflow step in same directory.

**Override behavior:** Use `$ARGUMENTS` to specify a different PRD or feature description for project planning if you want to plan something other than the workflow's current PRD.

## Example Usage

```
# Automatic mode (uses workflow PRD)
/project:feature-planning

# Override mode (plan specific feature)
/project:feature-planning user authentication system with enterprise SSO
/project:feature-planning real-time collaboration dashboard with microservices
/project:feature-planning mobile AI-powered performance monitoring platform
```

## Integration Notes

This command is the fourth step in the idea-to-task workflow:
`brainstorm ’ feature-proposal ’ feature-to-prd ’ feature-planning ’ task-creation`

Results from this command should provide comprehensive project planning documentation for detailed engineering task creation and sprint execution phases.