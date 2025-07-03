# Feature Proposal Output Template

## Agent Instructions

When executing `/project:feature-proposal`, use this template to structure your output. This ensures consistent, testable, and reproducible results that integrate seamlessly with `/project:feature-to-prd`.

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
- Brainstorm Integration: Read tool used to access [file path] - extracted [specific insights]
- Codebase Analysis: Grep/Glob/Read tools used to analyze [specific areas] - discovered [findings]
- External Research: WebSearch tool used to validate [specific aspects] - confirmed [patterns]

### Context
**Feature Overview:** [Clear description of the proposed feature]

**Business Justification:** [Why this feature is needed and its expected impact]

**Target Users:** [Primary and secondary user groups affected]

**Success Metrics:** [How success will be measured]

### Research
**Brainstorm Integration:**
- **Source Analysis:** [Reference to brainstorm output file if applicable]
- **Selected Ideas:** [Which brainstormed concepts are being developed]
- **Research Validation:** [Key findings from brainstorm research phase]

**Technical Feasibility:**
- **Current Architecture:** [How feature fits with existing system]
- **Similar Features:** [Existing implementations found in codebase]
- **Technical Dependencies:** [Required systems, APIs, or components]
- **Implementation Patterns:** [Industry best practices for similar features]

**Competitive Analysis:**
- **Market Research:** [How competitors handle similar features]
- **Differentiation:** [What makes this implementation unique]
- **Industry Standards:** [Relevant standards or conventions]

### Analysis
**Requirements Breakdown:**
1. **Functional Requirements**
   - **User Stories:** [As a user, I want...]
   - **Acceptance Criteria:** [Specific behaviors and outcomes]
   - **Success Scenarios:** [Happy path workflows]
   - **Edge Cases:** [Error conditions and boundaries]

2. **Non-Functional Requirements**
   - **Performance:** [Speed, scalability, resource usage]
   - **Security:** [Authentication, authorization, data protection]
   - **Accessibility:** [Compliance and inclusive design]
   - **Compatibility:** [Browser, device, platform support]

**Resource Assessment:**
- **Development Effort:** [Time estimates for implementation]
- **Design Requirements:** [UI/UX work needed]
- **Testing Strategy:** [Unit, integration, E2E testing needs]
- **Documentation:** [User guides, API docs, technical specs]

**Risk Analysis:**
- **Technical Risks:** [Implementation challenges and mitigation]
- **Business Risks:** [Market, timeline, resource constraints]
- **User Experience Risks:** [Adoption, usability concerns]
- **Mitigation Strategies:** [How to address identified risks]

### Recommendations
**Implementation Approach:** [Recommended development strategy]

**Priority Assessment:** [High/Medium/Low with justification]

**Timeline Estimation:** [Phases and milestones]

**Resource Allocation:** [Team members and skills needed]

**Alternative Approaches:** [Other viable implementation options]

**Minimum Viable Product (MVP):** [Core features for initial release]

### Integration
**PRD Preparation:**
- **Stakeholder Review:** [Who needs to approve this proposal]
- **Additional Requirements:** [What needs further specification]
- **Technical Specifications:** [Areas requiring detailed design]

**Command Transition:**
- **Ready for:** `/project:feature-to-prd [feature name]`
- **Required Inputs:** [What the next command needs from this output]
- **Success Handoff:** [Validation criteria for successful transition]

## Feasibility Matrix

| Criteria | Score (1-5) | Justification |
|----------|-------------|---------------|
| Technical Complexity | [1-5] | [Brief explanation] |
| Resource Availability | [1-5] | [Brief explanation] |
| Business Impact | [1-5] | [Brief explanation] |
| User Value | [1-5] | [Brief explanation] |
| Implementation Risk | [1-5] | [Brief explanation] |
| **Total Score** | **[Sum/25]** | **[Overall assessment]** |

## Command Execution Validation

### Module Access Validation
**REQUIRED:** Verify all modules were accessed and documented:
- [ ] @docs/modules/thinking-mode.md accessed and documented
- [ ] @docs/modules/workflow-integration.md accessed and documented  
- [ ] @docs/modules/tool-usage-patterns.md accessed and documented
- [ ] @docs/modules/template-integration.md accessed and documented
- [ ] @docs/modules/output-structure.md accessed and documented
- [ ] Previous brainstorm output accessed and integrated

### Tool Usage Validation
**REQUIRED:** Verify all tools were used and documented:
- [ ] Read tool used for brainstorm integration with specific file path
- [ ] Grep tool used for codebase analysis (minimum 1 search documented)
- [ ] Glob tool used for file pattern identification (minimum 1 search documented)
- [ ] Read tool used for architecture analysis (minimum 1 file analyzed)
- [ ] WebSearch tool used for external validation (minimum 1 search documented)
- [ ] Write tool used to create output file

### Content Quality Validation
**REQUIRED:** Verify all content requirements met:
- [ ] All user stories have acceptance criteria
- [ ] Technical feasibility is thoroughly assessed
- [ ] Resource requirements are realistic
- [ ] Risks are identified with mitigation strategies
- [ ] Success metrics are measurable
- [ ] Integration section prepares for PRD development
- [ ] Feasibility matrix is completed with all scores and justifications

### Template Compliance Validation
**REQUIRED:** Verify template structure followed:
- [ ] Extended Thinking Mode Documentation section completed
- [ ] All template sections included and populated
- [ ] No bracketed placeholders remain unfilled
- [ ] Feasibility matrix calculated correctly
- [ ] Integration section includes next command preparation
- [ ] File saved with correct naming convention

## File Output Instructions

Save this structured output using the Write tool with filename:
`feature-proposal-[feature-name]-[YYYY-MM-DD].md`

Example: `feature-proposal-user-auth-2024-07-03.md`

## Template Usage Notes

- Replace all bracketed placeholders with actual content
- Maintain the structure but adapt content length as needed
- Include links to brainstorm outputs and external sources
- Use bullet points and tables for clarity
- Ensure requirements are specific and testable
- Focus on actionable recommendations