# Feature Proposal Command Execution Checklist

## Pre-Execution Validation

### Environment Check
- [ ] Current working directory verified
- [ ] Previous brainstorm output exists in workflow directory
- [ ] Template files accessible at docs/templates/
- [ ] Module files accessible at docs/modules/

### Arguments Validation
- [ ] $ARGUMENTS captured (or default mode acknowledged)
- [ ] Workflow directory identified from previous brainstorm
- [ ] Topic keywords extracted for consistent naming

## Step-by-Step Execution Tracking

### Step 1: Extended Thinking Mode
- [ ] Read docs/modules/thinking-mode.md
- [ ] Activated visible reasoning process
- [ ] Documented module access in thinking section

### Step 2: Input Analysis Phase
- [ ] Read docs/modules/workflow-integration.md
- [ ] Read docs/modules/tool-usage-patterns.md  
- [ ] Documented module guidance in thinking section
- [ ] Read previous brainstorm output file
- [ ] Extracted specific insights with quotes/references
- [ ] Identified selected ideas from Recommendations section

### Step 3: Feature Scope Definition
- [ ] Grep tool used for codebase analysis (minimum 1 search)
- [ ] Glob tool used for file pattern identification (minimum 1 search)
- [ ] Read tool used for architecture analysis (minimum 1 file)
- [ ] WebSearch tool used for external validation (minimum 1 search)
- [ ] Each tool use documented with contribution analysis

### Step 4: Requirement Structuring
- [ ] User stories defined with acceptance criteria
- [ ] Technical requirements and dependencies identified
- [ ] Success metrics and validation criteria established
- [ ] Resource requirements and timeline estimates outlined

### Step 5: Feasibility Assessment
- [ ] Technical complexity evaluated against current architecture
- [ ] Resource requirements assessed (development, design, testing)
- [ ] Risks identified with mitigation strategies
- [ ] Alternative approaches compared from brainstorm phase

### Step 6: Structured Presentation
- [ ] Read docs/modules/template-integration.md
- [ ] Read docs/modules/output-structure.md
- [ ] Read docs/templates/feature-proposal-output-template.md
- [ ] Template structure followed exactly
- [ ] All bracketed placeholders replaced

### Step 7: Workflow Integration & Validation
- [ ] Read docs/modules/workflow-integration.md
- [ ] Integration section prepared for /project:feature-to-prd
- [ ] Validation checklist completed
- [ ] File created with Write tool in correct directory

## Content Quality Verification

### Required Sections Check
- [ ] Extended Thinking Mode Documentation section completed
- [ ] Context section with feature overview, business justification, target users, success metrics
- [ ] Research section with brainstorm integration, technical feasibility, competitive analysis
- [ ] Analysis section with requirements breakdown, resource assessment, risk analysis
- [ ] Recommendations section with implementation approach, priority, timeline, alternatives, MVP
- [ ] Integration section with PRD preparation and command transition
- [ ] Feasibility matrix with all scores and total calculation
- [ ] Command Execution Validation section with all checklists completed

### User Stories Validation
- [ ] Each user story follows "As a [user], I want [goal] so that [benefit]" format
- [ ] Each user story has specific acceptance criteria
- [ ] Success scenarios and edge cases defined
- [ ] Stories are testable and measurable

### Risk Assessment Validation
- [ ] Technical risks identified with mitigation strategies
- [ ] Business risks identified with mitigation strategies  
- [ ] User experience risks identified with mitigation strategies
- [ ] Each risk has realistic mitigation approach

## Final Output Validation

### File Structure Check
- [ ] File saved in docs/outputs/sessions/[YYYY-MM-DD]/workflow-[NN]-[topic]/ directory
- [ ] Filename follows feature-proposal-[topic]-[YYYY-MM-DD].md convention
- [ ] Topic consistency maintained from brainstorm command
- [ ] File created successfully with Write tool

### Template Compliance Check
- [ ] All template sections present and populated
- [ ] No [bracketed placeholders] remain unfilled
- [ ] Feasibility matrix scores total calculated correctly
- [ ] Validation checklist included and completed
- [ ] Integration section specifies next command requirements

### Integration Readiness Check
- [ ] Command transition clearly states: "Ready for: /project:feature-to-prd [feature name]"
- [ ] Required inputs for next command specified
- [ ] Success handoff criteria defined
- [ ] Context preserved for PRD development

## Quality Scoring

### Module Access (20 points)
- [ ] All 5 required modules accessed and documented (4 pts each)

### Tool Usage (20 points)  
- [ ] Brainstorm integration with Read tool (5 pts)
- [ ] Codebase analysis with Grep/Glob/Read tools (10 pts)
- [ ] External research with WebSearch tool (5 pts)

### Content Completeness (40 points)
- [ ] All template sections completed substantively (20 pts)
- [ ] User stories with acceptance criteria (5 pts)
- [ ] Risk assessment with mitigation strategies (5 pts)
- [ ] Feasibility matrix accurate and complete (5 pts)
- [ ] Integration section ready for next command (5 pts)

### Process Compliance (20 points)
- [ ] Extended thinking mode documented (5 pts)
- [ ] Tool usage logged with contributions (5 pts)
- [ ] Validation checklist completed (5 pts)
- [ ] File output correct location and naming (5 pts)

**TOTAL SCORE: ___/100 points**
**PASS CRITERIA: 85/100 points** (Raised from 80 due to enhanced requirements)

## Common Failure Points to Avoid

### Critical Failures (Automatic Fail)
- Missing validation checklist completion in output
- Template sections incomplete or missing
- File created in wrong directory or incorrect naming
- User stories without acceptance criteria
- Brainstorm output not accessed or integrated

### Major Issues (10+ point deductions)
- Module access not documented in thinking mode
- Tool usage not logged with contribution analysis
- Risk assessment missing mitigation strategies
- Feasibility matrix incomplete or inaccurate
- Integration section missing next command preparation

### Minor Issues (5 point deductions)
- Placeholder text not fully replaced
- Timeline estimates unrealistic or vague
- Success metrics not measurable
- Alternative approaches not considered
- Topic consistency breaks from previous command