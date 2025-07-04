# Feature to PRD Output Template

## Agent Instructions

When executing `/project:feature-to-prd`, use this template to structure your output. This ensures consistent, testable, and reproducible results that integrate seamlessly with `/project:feature-planning`.

**Module References:**
- Extended thinking: @docs/modules/thinking-mode.md
- Tool usage: @docs/modules/tool-usage-patterns.md  
- Output structure: @docs/modules/output-structure.md
- Template integration: @docs/modules/template-integration.md
- Workflow integration: @docs/modules/workflow-integration.md

## Required Output Structure

### Extended Thinking Mode Documentation
**Module Access Log:** [Document each module accessed with Read tool]
- @docs/modules/thinking-mode.md: [Brief note on activation]
- @docs/modules/workflow-integration.md: [Brief note on guidance received]
- @docs/modules/tool-usage-patterns.md: [Brief note on tool sequence guidance]
- @docs/modules/template-integration.md: [Brief note on template requirements]
- @docs/modules/output-structure.md: [Brief note on structure requirements]

**Tool Usage Log:** [Document each tool use and its contribution]
- Feature Proposal Integration: Read tool used to access [file path] - extracted [specific requirements]
- Stakeholder Analysis: Grep/Glob/Read tools used to analyze [specific areas] - discovered [business context]
- Market Research: WebSearch tool used to validate [specific aspects] - confirmed [positioning]

### Executive Summary
**Product Overview:** [Concise description of the feature and its purpose]

**Business Objectives:** [Primary business goals this feature will achieve]

**Target Users:** [Detailed user segments and personas affected]

**Success Metrics:** [Key performance indicators and measurable outcomes]

**Timeline Overview:** [High-level implementation phases and milestones]

### Business Context
**Problem Statement:**
- **Current State:** [Description of existing situation or gap]
- **Pain Points:** [Specific user and business challenges addressed]
- **Market Opportunity:** [Business value and competitive advantage]

**Business Justification:**
- **Revenue Impact:** [Expected financial outcomes]
- **Cost Analysis:** [Development investment vs. expected returns]
- **Strategic Alignment:** [How feature supports broader business goals]
- **Risk Assessment:** [Business risks and mitigation strategies]

**Competitive Analysis:**
- **Market Position:** [Where this feature positions the product]
- **Competitor Benchmarks:** [How similar features perform in the market]
- **Differentiation Strategy:** [What makes this implementation unique]
- **Market Validation:** [Evidence supporting feature demand]

### Stakeholder Analysis
**Stakeholder Matrix:**

| Stakeholder Group | Role | Interest Level | Influence | Communication Strategy |
|------------------|------|----------------|-----------|----------------------|
| [Business Owner] | [Decision maker] | [High/Medium/Low] | [High/Medium/Low] | [How to engage] |
| [Product Manager] | [Feature owner] | [High/Medium/Low] | [High/Medium/Low] | [How to engage] |
| [Engineering Team] | [Implementation] | [High/Medium/Low] | [High/Medium/Low] | [How to engage] |
| [Design Team] | [User experience] | [High/Medium/Low] | [High/Medium/Low] | [How to engage] |
| [QA Team] | [Quality assurance] | [High/Medium/Low] | [High/Medium/Low] | [How to engage] |
| [End Users] | [Feature users] | [High/Medium/Low] | [High/Medium/Low] | [How to engage] |

**Communication Plan:**
- **Review Cycles:** [Frequency and format of stakeholder reviews]
- **Approval Process:** [Decision-making workflow and gates]
- **Feedback Collection:** [Methods for gathering stakeholder input]
- **Conflict Resolution:** [Process for resolving disagreements]

### Detailed Requirements
**Functional Requirements:**
1. **Core Features**
   - **User Stories:** [Detailed "As a [user], I want [goal] so that [benefit]"]
   - **Acceptance Criteria:** [Specific, measurable behaviors and outcomes]
   - **Business Rules:** [Logic and constraints governing feature behavior]
   - **Data Requirements:** [Information needed and how it flows]

2. **User Experience Requirements**
   - **User Interface Specifications:** [Layout, interaction patterns, visual design]
   - **User Journey Mapping:** [Step-by-step user workflows]
   - **Accessibility Requirements:** [WCAG compliance and inclusive design]
   - **Mobile/Responsive Considerations:** [Cross-platform experience requirements]

**Non-Functional Requirements:**
1. **Performance Requirements**
   - **Speed:** [Response time expectations and SLAs]
   - **Scalability:** [Concurrent user and data volume expectations]
   - **Resource Usage:** [Memory, CPU, storage constraints]
   - **Reliability:** [Uptime and error rate expectations]

2. **Security Requirements**
   - **Authentication:** [User verification and access control]
   - **Authorization:** [Permission levels and role-based access]
   - **Data Protection:** [Encryption, privacy, and compliance requirements]
   - **Audit Trail:** [Logging and monitoring requirements]

3. **Integration Requirements**
   - **API Specifications:** [External service integrations]
   - **Database Requirements:** [Data storage and migration needs]
   - **Third-Party Dependencies:** [External tools and services required]
   - **Backward Compatibility:** [Legacy system integration constraints]

### Technical Specifications
**Architecture Overview:**
- **System Architecture:** [High-level technical design and component interaction]
- **Database Design:** [Data model and schema requirements]
- **API Design:** [Endpoint specifications and data contracts]
- **Technology Stack:** [Languages, frameworks, and tools to be used]

**Implementation Details:**
- **Development Phases:** [Technical milestones and deliverables]
- **Code Quality Standards:** [Coding conventions and review processes]
- **Testing Strategy:** [Unit, integration, and end-to-end testing approaches]
- **Deployment Strategy:** [Release process and environment requirements]

**Security and Compliance:**
- **Security Architecture:** [Technical security measures and protocols]
- **Compliance Requirements:** [Regulatory and industry standards]
- **Data Governance:** [Data handling and retention policies]
- **Monitoring and Alerting:** [Operational visibility and incident response]

### Success Criteria and Metrics
**Key Performance Indicators (KPIs):**
- **Business Metrics:** [Revenue, conversion, retention measurements]
- **Technical Metrics:** [Performance, reliability, scalability measurements]
- **User Metrics:** [Adoption, satisfaction, engagement measurements]
- **Quality Metrics:** [Bug rates, support ticket volumes, user feedback]

**Measurement Plan:**
- **Baseline Metrics:** [Current state measurements for comparison]
- **Target Metrics:** [Specific goals and success thresholds]
- **Measurement Timeline:** [When and how metrics will be collected]
- **Reporting Framework:** [How results will be communicated to stakeholders]

**Success Validation:**
- **Launch Criteria:** [Requirements for feature release]
- **Success Thresholds:** [Minimum acceptable performance levels]
- **Monitoring Plan:** [Post-launch measurement and optimization]
- **Iteration Strategy:** [Process for feature refinement based on metrics]

### Implementation Planning
**Resource Requirements:**
- **Development Team:** [Required skills, roles, and time allocation]
- **Design Resources:** [UI/UX design requirements and timeline]
- **Infrastructure Needs:** [Hardware, software, and service requirements]
- **Budget Allocation:** [Cost breakdown and financial planning]

**Timeline and Milestones:**
- **Phase 1: [Phase Name]** - [Duration] - [Deliverables and success criteria]
- **Phase 2: [Phase Name]** - [Duration] - [Deliverables and success criteria]
- **Phase 3: [Phase Name]** - [Duration] - [Deliverables and success criteria]
- **Launch:** [Target date] - [Launch criteria and rollout plan]

**Risk Management:**
- **Technical Risks:** [Implementation challenges and mitigation strategies]
- **Business Risks:** [Market, timeline, and resource risks]
- **User Adoption Risks:** [Usability and adoption challenges]
- **Contingency Plans:** [Fallback strategies for major risks]

### Integration
**Feature Planning Preparation:**
- **Task Breakdown:** [High-level work packages identified]
- **Dependencies:** [Prerequisites and blocking factors]
- **Resource Assignments:** [Team member responsibilities]
- **Communication Protocols:** [How teams will coordinate]

**Command Transition:**
- **Ready for:** `/project:feature-planning [feature name]`
- **Required Inputs:** [What the next command needs from this PRD]
- **Success Handoff:** [Validation criteria for successful transition]

## Command Execution Validation

### Module Access Validation
**REQUIRED:** Verify all modules were accessed and documented:
- [ ] @docs/modules/thinking-mode.md accessed and documented
- [ ] @docs/modules/workflow-integration.md accessed and documented  
- [ ] @docs/modules/tool-usage-patterns.md accessed and documented
- [ ] @docs/modules/template-integration.md accessed and documented
- [ ] @docs/modules/output-structure.md accessed and documented
- [ ] Previous feature-proposal output accessed and integrated

### Tool Usage Validation
**REQUIRED:** Verify all tools were used and documented:
- [ ] Read tool used for feature proposal integration with specific file path
- [ ] Grep tool used for stakeholder documentation discovery (minimum 1 search documented)
- [ ] Glob tool used for business context file identification (minimum 1 search documented)
- [ ] Read tool used for stakeholder analysis (minimum 1 file analyzed)
- [ ] WebSearch tool used for market validation (minimum 1 search documented)
- [ ] Write tool used to create PRD output file

### Content Quality Validation
**REQUIRED:** Verify all content requirements met:
- [ ] All business objectives have measurable success criteria
- [ ] Technical specifications are implementation-ready
- [ ] Stakeholder responsibilities are clearly defined
- [ ] Resource requirements are realistic and detailed
- [ ] Timeline includes specific milestones and deliverables
- [ ] Risk management strategies are comprehensive
- [ ] Integration section prepares for feature planning development

### PRD Structure Validation
**REQUIRED:** Verify PRD completeness:
- [ ] Executive summary provides clear product overview
- [ ] Business context justifies feature development
- [ ] Stakeholder matrix includes all relevant parties
- [ ] Functional and non-functional requirements are comprehensive
- [ ] Technical specifications are architecture-ready
- [ ] Success criteria include measurable KPIs
- [ ] Implementation planning includes timeline and resources

### Template Compliance Validation
**REQUIRED:** Verify template structure followed:
- [ ] Extended Thinking Mode Documentation section completed
- [ ] All template sections included and populated
- [ ] No bracketed placeholders remain unfilled
- [ ] Stakeholder matrix is complete with communication strategies
- [ ] Integration section includes next command preparation
- [ ] File saved with correct naming convention

## File Output Instructions

Save this structured output using the Write tool with filename:
`feature-to-prd-[feature-name]-[YYYY-MM-DD].md`

Example: `feature-to-prd-user-auth-2024-07-03.md`

## Template Usage Notes

- Replace all bracketed placeholders with actual content
- Maintain the structure but adapt content length as needed
- Include specific metrics and measurable outcomes throughout
- Focus on business impact and stakeholder value
- Ensure technical specifications are actionable for engineering teams
- Use tables and bullet points for clarity and scannability
- Link to feature proposal outputs and external sources for validation