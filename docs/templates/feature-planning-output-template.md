# Feature Planning Output Template

## Agent Instructions

When executing `/project:feature-planning`, use this template to structure your output. This ensures consistent, testable, and reproducible results that integrate seamlessly with `/project:task-creation`.

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
- PRD Integration: Read tool used to access [file path] - extracted [specific project requirements]
- Project Planning Research: Grep/Glob/Read tools used to analyze [planning methodologies] - discovered [development context]
- Methodology Validation: WebSearch tool used to validate [project management approaches] - confirmed [best practices]

### Executive Summary
**Project Overview:** [Comprehensive description of the development project and its technical scope]

**Engineering Objectives:** [Primary technical and delivery goals this project will achieve]

**Development Approach:** [Technical methodology and implementation strategy]

**Success Metrics:** [Key performance indicators for project delivery and quality]

**Timeline Overview:** [High-level development phases, sprints, and milestone delivery]

### Project Scope and Architecture Planning
**Project Scope Definition:**
- **Technical Scope:** [Detailed breakdown of technical deliverables and system components]
- **Feature Boundaries:** [Clear definition of included/excluded functionality]
- **Implementation Boundaries:** [Development constraints and technical limitations]
- **Quality Standards:** [Code quality, testing, and performance requirements]

**Technical Architecture Planning:**
- **System Design:** [Architecture patterns, technology stack decisions, component structure]
- **Integration Architecture:** [External dependencies, API integrations, data flow design]
- **Infrastructure Requirements:** [Development, testing, and production environment needs]
- **Technical Standards:** [Coding standards, documentation requirements, review processes]

**Development Environment Planning:**
- **Development Tools:** [IDE setup, development framework configuration, debugging tools]
- **CI/CD Pipeline:** [Build automation, testing pipeline, deployment processes]
- **Testing Infrastructure:** [Unit testing, integration testing, performance testing setup]
- **Documentation System:** [Code documentation, API documentation, user documentation]

### Engineering Task Breakdown Structure
**Work Breakdown Structure (WBS):**

#### Phase 1: [Phase Name] - [Duration]
**Technical Deliverables:**
- **Task 1.1:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]
- **Task 1.2:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]
- **Task 1.3:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]

**Dependencies:** [Technical prerequisites and blocking factors]
**Success Criteria:** [Measurable completion criteria for phase]

#### Phase 2: [Phase Name] - [Duration]
**Technical Deliverables:**
- **Task 2.1:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]
- **Task 2.2:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]
- **Task 2.3:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]

**Dependencies:** [Technical prerequisites and blocking factors]
**Success Criteria:** [Measurable completion criteria for phase]

#### Phase 3: [Phase Name] - [Duration]
**Technical Deliverables:**
- **Task 3.1:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]
- **Task 3.2:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]
- **Task 3.3:** [Task Name] - [Description] - [Effort Estimate] - [Acceptance Criteria]

**Dependencies:** [Technical prerequisites and blocking factors]
**Success Criteria:** [Measurable completion criteria for phase]

**Critical Path Analysis:**
- **Critical Tasks:** [Tasks that directly impact project timeline]
- **Parallel Opportunities:** [Tasks that can be executed simultaneously]
- **Bottleneck Identification:** [Resource constraints and technical dependencies]
- **Timeline Optimization:** [Strategies for efficient task sequencing]

### Resource Allocation and Timeline Planning
**Engineering Team Requirements:**

| Role | Skill Requirements | Time Allocation | Key Responsibilities |
|------|-------------------|----------------|---------------------|
| [Lead Developer] | [Technical skills needed] | [% time or hours] | [Primary responsibilities] |
| [Frontend Developer] | [Technical skills needed] | [% time or hours] | [Primary responsibilities] |
| [Backend Developer] | [Technical skills needed] | [% time or hours] | [Primary responsibilities] |
| [DevOps Engineer] | [Technical skills needed] | [% time or hours] | [Primary responsibilities] |
| [QA Engineer] | [Technical skills needed] | [% time or hours] | [Primary responsibilities] |
| [UI/UX Designer] | [Technical skills needed] | [% time or hours] | [Primary responsibilities] |

**Effort Estimation:**
- **Development Effort:** [Total development hours/story points breakdown]
- **Testing Effort:** [QA, automation, and validation time requirements]
- **Code Review Effort:** [Review cycles and peer validation time]
- **Documentation Effort:** [Technical documentation and knowledge transfer time]

**Project Timeline:**

| Week | Phase | Key Deliverables | Resource Allocation | Success Criteria |
|------|-------|-----------------|-------------------|------------------|
| Week 1-2 | [Phase Name] | [Deliverable list] | [Team allocation] | [Completion criteria] |
| Week 3-4 | [Phase Name] | [Deliverable list] | [Team allocation] | [Completion criteria] |
| Week 5-6 | [Phase Name] | [Deliverable list] | [Team allocation] | [Completion criteria] |
| Week 7-8 | [Phase Name] | [Deliverable list] | [Team allocation] | [Completion criteria] |

**Sprint Planning:**
- **Sprint Duration:** [Sprint length and cadence]
- **Sprint Goals:** [Specific objectives for each sprint]
- **Sprint Deliverables:** [Expected output per sprint]
- **Sprint Reviews:** [Demo and feedback collection process]

### Risk Management and Mitigation Planning
**Technical Risk Assessment:**

| Risk Category | Risk Description | Probability | Impact | Mitigation Strategy | Contingency Plan |
|--------------|------------------|-------------|--------|-------------------|------------------|
| **Technical Complexity** | [Specific technical challenges] | [High/Medium/Low] | [High/Medium/Low] | [Prevention approach] | [Fallback strategy] |
| **Integration Challenges** | [System integration issues] | [High/Medium/Low] | [High/Medium/Low] | [Prevention approach] | [Fallback strategy] |
| **Performance Issues** | [Scalability and performance risks] | [High/Medium/Low] | [High/Medium/Low] | [Prevention approach] | [Fallback strategy] |
| **Security Vulnerabilities** | [Security implementation risks] | [High/Medium/Low] | [High/Medium/Low] | [Prevention approach] | [Fallback strategy] |

**Implementation Risk Management:**
- **Dependency Risks:** [External dependency failures and mitigation]
- **Resource Risks:** [Team availability and skill gap management]
- **Timeline Risks:** [Schedule compression and scope management]
- **Quality Risks:** [Technical debt and quality assurance strategies]

**Monitoring and Alerting:**
- **Progress Tracking:** [Daily/weekly progress monitoring methods]
- **Quality Metrics:** [Code quality, test coverage, bug rate monitoring]
- **Performance Monitoring:** [System performance and user experience tracking]
- **Risk Indicators:** [Early warning signs and escalation procedures]

### Quality Assurance and Testing Strategy
**Testing Framework:**
- **Unit Testing:** [Framework, coverage requirements, automation strategy]
- **Integration Testing:** [API testing, system integration validation]
- **End-to-End Testing:** [User workflow validation, acceptance testing]
- **Performance Testing:** [Load testing, stress testing, scalability validation]

**Code Quality Standards:**
- **Code Review Process:** [Peer review, automated review, approval workflow]
- **Coding Standards:** [Style guides, documentation requirements, best practices]
- **Technical Debt Management:** [Debt identification, prioritization, resolution]
- **Security Review:** [Security testing, vulnerability assessment, compliance validation]

**Quality Metrics and Monitoring:**
- **Coverage Metrics:** [Test coverage targets and measurement]
- **Quality Gates:** [Quality criteria for release approval]
- **Bug Tracking:** [Defect identification, prioritization, resolution tracking]
- **Performance Benchmarks:** [Performance targets and measurement criteria]

### Implementation Methodology and Best Practices
**Development Methodology:**
- **Agile Framework:** [Scrum/Kanban methodology and ceremonies]
- **Development Process:** [Feature development workflow and branching strategy]
- **Collaboration Tools:** [Communication, project management, documentation tools]
- **Knowledge Management:** [Documentation standards, knowledge sharing processes]

**Technical Best Practices:**
- **Architecture Principles:** [Design patterns, architectural guidelines, scalability principles]
- **Code Organization:** [Project structure, module organization, dependency management]
- **Documentation Standards:** [Code comments, API documentation, technical specifications]
- **Version Control:** [Git workflow, branching strategy, release management]

**Continuous Improvement:**
- **Retrospectives:** [Sprint retrospectives and process improvement]
- **Metrics Analysis:** [Performance analysis and optimization opportunities]
- **Feedback Integration:** [Stakeholder feedback incorporation and iteration]
- **Process Refinement:** [Development process optimization and tooling updates]

### Integration
**Task Creation Preparation:**
- **Detailed Task Breakdown:** [Specific engineering tasks ready for creation]
- **Task Dependencies:** [Prerequisites and blocking factors for each task]
- **Resource Assignments:** [Team member responsibilities and skill matching]
- **Sprint Allocation:** [Task distribution across development sprints]

**Command Transition:**
- **Ready for:** `/project:task-creation [feature name]`
- **Required Inputs:** [What the next command needs from this project plan]
- **Success Handoff:** [Validation criteria for successful transition to task creation]

## Command Execution Validation

### Module Access Validation
**REQUIRED:** Verify all modules were accessed and documented:
- [ ] @docs/modules/thinking-mode.md accessed and documented
- [ ] @docs/modules/workflow-integration.md accessed and documented  
- [ ] @docs/modules/tool-usage-patterns.md accessed and documented
- [ ] @docs/modules/template-integration.md accessed and documented
- [ ] @docs/modules/output-structure.md accessed and documented
- [ ] Previous feature-to-prd output accessed and integrated

### Tool Usage Validation
**REQUIRED:** Verify all tools were used and documented:
- [ ] Read tool used for PRD integration with specific file path
- [ ] Grep tool used for project planning discovery (minimum 1 search documented)
- [ ] Glob tool used for development methodology discovery (minimum 1 search documented)
- [ ] Read tool used for methodology analysis (minimum 1 file analyzed)
- [ ] WebSearch tool used for project management validation (minimum 1 search documented)
- [ ] Write tool used to create project plan output file

### Content Quality Validation
**REQUIRED:** Verify all content requirements met:
- [ ] All engineering objectives have measurable success criteria
- [ ] Technical specifications are implementation-ready
- [ ] Resource allocation is realistic and achievable
- [ ] Timeline includes adequate buffer for testing and iteration
- [ ] Risk management strategies are comprehensive with mitigation plans
- [ ] Quality assurance plan includes testing strategy and review processes
- [ ] Integration section prepares for task creation development

### Project Plan Structure Validation
**REQUIRED:** Verify project plan completeness:
- [ ] Executive summary provides clear project overview
- [ ] Project scope defines technical boundaries and deliverables
- [ ] Engineering task breakdown is comprehensive and actionable
- [ ] Resource allocation includes specific roles and time estimates
- [ ] Timeline planning includes phases, milestones, and dependencies
- [ ] Risk management includes technical, business, and adoption risks
- [ ] Quality assurance strategy includes testing and review processes

### Template Compliance Validation
**REQUIRED:** Verify template structure followed:
- [ ] Extended Thinking Mode Documentation section completed
- [ ] All template sections included and populated
- [ ] No bracketed placeholders remain unfilled
- [ ] Resource allocation matrix is complete with roles and responsibilities
- [ ] Integration section includes next command preparation
- [ ] File saved with correct naming convention

## File Output Instructions

Save this structured output using the Write tool with filename:
`feature-planning-[feature-name]-[YYYY-MM-DD].md`

Example: `feature-planning-user-auth-2024-07-03.md`

## Template Usage Notes

- Replace all bracketed placeholders with actual content
- Maintain the structure but adapt content length as needed
- Include specific effort estimates and measurable delivery criteria throughout
- Focus on engineering execution and technical implementation planning
- Ensure task breakdown is actionable for development teams
- Use tables and bullet points for clarity and project management efficiency
- Link to PRD outputs and project management methodologies for validation