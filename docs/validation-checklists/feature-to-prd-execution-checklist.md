# Feature to PRD Command Execution Checklist

## Pre-Execution Validation

### Environment Check
- [ ] Current working directory verified
- [ ] Previous feature-proposal output exists in workflow directory
- [ ] Template files accessible at docs/templates/
- [ ] Module files accessible at docs/modules/
- [ ] Stakeholder documentation accessible (if available)

### Arguments Validation
- [ ] $ARGUMENTS captured (or default mode acknowledged)
- [ ] Workflow directory identified from previous feature-proposal
- [ ] Topic keywords extracted for consistent naming
- [ ] Feature proposal file identified for integration

## Step-by-Step Execution Tracking

### Step 1: Extended Thinking Mode
- [ ] Read docs/modules/thinking-mode.md
- [ ] Activated visible reasoning process
- [ ] Documented module access in thinking section

### Step 2: Input Analysis Phase
- [ ] Read docs/modules/workflow-integration.md
- [ ] Read docs/modules/tool-usage-patterns.md  
- [ ] Documented module guidance in thinking section
- [ ] Read previous feature-proposal output file
- [ ] Extracted technical requirements with quotes/references
- [ ] Extracted user stories and acceptance criteria
- [ ] Documented success metrics from proposal

### Step 3: Stakeholder Analysis
- [ ] Grep tool used for stakeholder documentation discovery (minimum 1 search)
- [ ] Glob tool used for business context file identification (minimum 1 search)
- [ ] Read tool used for stakeholder analysis (minimum 1 file)
- [ ] WebSearch tool used for market validation (minimum 1 search)
- [ ] Each tool use documented with contribution analysis

### Step 4: Business Context Development
- [ ] Business objectives defined with measurable success criteria
- [ ] Target user segments and stakeholder groups identified
- [ ] Market positioning and competitive differentiators established
- [ ] Business impact metrics and validation methods outlined

### Step 5: Technical Specification Refinement
- [ ] Technical requirements expanded from feature proposal
- [ ] System architecture and integration points defined
- [ ] Performance requirements and constraints specified
- [ ] Security, compliance, and accessibility requirements identified

### Step 6: Stakeholder Communication Planning
- [ ] Stakeholder-specific communication strategies created
- [ ] Review cycles and approval processes defined
- [ ] Feedback collection and iteration methods established
- [ ] Cross-functional collaboration requirements planned

### Step 7: Structured PRD Presentation
- [ ] Read docs/modules/template-integration.md
- [ ] Read docs/modules/output-structure.md
- [ ] Read docs/templates/feature-to-prd-output-template.md
- [ ] Template structure followed exactly
- [ ] All bracketed placeholders replaced

### Step 8: Workflow Integration & Validation
- [ ] Read docs/modules/workflow-integration.md
- [ ] Integration section prepared for /project:feature-planning
- [ ] Validation checklist completed
- [ ] File created with Write tool in correct directory

## Content Quality Verification

### Required Sections Check
- [ ] Extended Thinking Mode Documentation section completed
- [ ] Executive Summary with product overview, business objectives, target users, success metrics, timeline
- [ ] Business Context with problem statement, business justification, competitive analysis
- [ ] Stakeholder Analysis with stakeholder matrix and communication plan
- [ ] Detailed Requirements with functional and non-functional requirements
- [ ] Technical Specifications with architecture overview, implementation details, security
- [ ] Success Criteria and Metrics with KPIs, measurement plan, success validation
- [ ] Implementation Planning with resource requirements, timeline, risk management
- [ ] Integration section with feature planning preparation and command transition
- [ ] Command Execution Validation section with all checklists completed

### Business Requirements Validation
- [ ] Each business objective has measurable success criteria
- [ ] Target user segments are clearly defined with personas
- [ ] Market positioning is supported by competitive analysis
- [ ] Business impact is quantified with specific metrics
- [ ] Revenue and cost analysis included where applicable

### Stakeholder Matrix Validation
- [ ] All relevant stakeholder groups identified
- [ ] Interest and influence levels assessed for each stakeholder
- [ ] Communication strategies defined for each stakeholder group
- [ ] Review cycles and approval processes clearly defined
- [ ] Conflict resolution processes established

### Technical Requirements Validation
- [ ] Functional requirements derived from feature proposal user stories
- [ ] Non-functional requirements include performance, security, accessibility
- [ ] System architecture and integration points specified
- [ ] API specifications and data contracts defined where relevant
- [ ] Technology stack and implementation approach documented

### Implementation Planning Validation
- [ ] Resource requirements detailed with specific roles and time allocation
- [ ] Timeline includes specific phases, milestones, and deliverables
- [ ] Budget allocation and cost breakdown provided
- [ ] Risk management includes technical, business, and adoption risks
- [ ] Each risk has specific mitigation strategies

## Final Output Validation

### File Structure Check
- [ ] File saved in docs/outputs/sessions/[YYYY-MM-DD]/workflow-[NN]-[topic]/ directory
- [ ] Filename follows feature-to-prd-[topic]-[YYYY-MM-DD].md convention
- [ ] Topic consistency maintained from feature-proposal command
- [ ] File created successfully with Write tool

### Template Compliance Check
- [ ] All template sections present and populated
- [ ] No [bracketed placeholders] remain unfilled
- [ ] Stakeholder matrix is complete with all roles and communication strategies
- [ ] Validation checklist included and completed
- [ ] Integration section specifies next command requirements

### Integration Readiness Check
- [ ] Command transition clearly states: "Ready for: /project:feature-planning [feature name]"
- [ ] Required inputs for next command specified
- [ ] Success handoff criteria defined
- [ ] PRD structure ready for engineering planning consumption

## Quality Scoring System (100 Points)

### Process Compliance (25 points)
- [ ] Extended thinking mode activated and documented (5 pts)
- [ ] All required modules accessed with Read tool and documented (5 pts)
- [ ] All mandatory tool sequences executed and documented (5 pts)
- [ ] Feature proposal integration completed with specific references (5 pts)
- [ ] File output created in correct location with proper naming (5 pts)

### Module Integration (20 points)
- [ ] Thinking mode module guidance followed and documented (4 pts)
- [ ] Workflow integration module guidance applied (4 pts)
- [ ] Tool usage patterns module guidance followed (4 pts)
- [ ] Template integration module requirements met (4 pts)
- [ ] Output structure module standards applied (4 pts)

### Research Quality (25 points)
- [ ] Stakeholder analysis comprehensive with discovery tools (5 pts)
- [ ] Business context analysis thorough with market research (5 pts)
- [ ] Technical specification refinement substantial and detailed (5 pts)
- [ ] Competitive analysis includes market validation research (5 pts)
- [ ] Cross-reference validation between all research sources (5 pts)

### Output Quality (30 points)
- [ ] Executive summary clear and comprehensive (5 pts)
- [ ] Business context includes problem statement, justification, competitive analysis (5 pts)
- [ ] Stakeholder matrix complete with communication strategies (5 pts)
- [ ] Requirements detailed with functional and non-functional specifications (5 pts)
- [ ] Technical specifications implementation-ready for engineering (5 pts)
- [ ] Implementation planning includes timeline, resources, risk management (5 pts)

**TOTAL SCORE: ___/100 points**
**PASS CRITERIA: 85/100 points** (Following enhanced validation standards)

## Scoring Rubric Details

### Excellent (5/5 points per criterion)
- Complete, thorough, and exceeds requirements
- Comprehensive analysis with detailed supporting evidence
- Clear, actionable, and implementation-ready content
- Perfect integration with workflow and template requirements

### Good (4/5 points per criterion)
- Complete and meets requirements
- Adequate analysis with supporting evidence
- Clear and actionable content
- Good integration with minor gaps

### Satisfactory (3/5 points per criterion)
- Mostly complete with minor gaps
- Basic analysis with some supporting evidence
- Generally clear with some ambiguity
- Adequate integration with some inconsistencies

### Needs Improvement (2/5 points per criterion)
- Partially complete with notable gaps
- Limited analysis with minimal supporting evidence
- Unclear or difficult to act upon
- Poor integration with significant inconsistencies

### Inadequate (1/5 points per criterion)
- Incomplete or missing critical elements
- No analysis or unsupported claims
- Unclear, unusable, or contradictory content
- No integration or major workflow breaks

## Common Failure Points to Avoid

### Critical Failures (Automatic Fail)
- Missing validation checklist completion in output
- Template sections incomplete or missing
- File created in wrong directory or incorrect naming
- Business objectives without measurable success criteria
- Feature proposal output not accessed or integrated
- Stakeholder matrix incomplete or missing

### Major Issues (10+ point deductions)
- Module access not documented in thinking mode
- Tool usage not logged with contribution analysis
- Risk management missing mitigation strategies
- Technical specifications not implementation-ready
- Integration section missing next command preparation
- Business context missing competitive analysis

### Minor Issues (5 point deductions)
- Placeholder text not fully replaced
- Timeline estimates unrealistic or vague
- Success metrics not measurable
- Stakeholder communication strategies unclear
- Topic consistency breaks from previous command
- Missing cross-references between sections

## PRD-Specific Validation Criteria

### Business Impact Focus
- [ ] Clear ROI and business value proposition
- [ ] Market opportunity quantified with supporting data
- [ ] Competitive positioning clearly articulated
- [ ] Success metrics tied to business objectives

### Stakeholder Readiness
- [ ] All key stakeholders identified and analyzed
- [ ] Communication and approval processes defined
- [ ] Review cycles and feedback mechanisms established
- [ ] Cross-functional collaboration requirements planned

### Implementation Readiness
- [ ] Technical specifications detailed enough for engineering planning
- [ ] Resource requirements realistic and justified
- [ ] Timeline includes specific milestones and deliverables
- [ ] Risk management comprehensive with concrete mitigation plans

### Engineering Handoff Quality
- [ ] Technical architecture clearly defined
- [ ] Integration points and dependencies specified
- [ ] Performance and security requirements detailed
- [ ] Quality assurance and testing strategy outlined