# Brainstorm Output Template

## Agent Instructions

When executing `/project:brainstorm`, use this template to structure your output. This ensures consistent, testable, and reproducible results that integrate seamlessly with `/project:feature-proposal`.

**Module References:**
- Extended thinking: @docs/modules/thinking-mode.md
- Tool usage: @docs/modules/tool-usage-patterns.md  
- Output structure: @docs/modules/output-structure.md
- Workflow integration: @docs/modules/workflow-integration.md

## Required Output Structure

### Extended Thinking Mode Documentation (Optional)
**Research Process Log:** [Document key research decisions and tool findings if helpful for handoff]
- Module Access: [Note any modules referenced and key guidance received]
- Tool Usage: [Document significant tool findings that inform recommendations]
- Decision Points: [Log major research decisions and rationale]

### Context
**Problem Statement:** [Clear description of the challenge being addressed]

**Scope:** [Boundaries and limitations of the brainstorming session]

**Success Criteria:** [What constitutes a successful brainstorming outcome]

### Research
**Codebase Analysis:**
- **Related Implementations:** [List files, functions, or patterns found using Grep/Glob tools]
- **Current Architecture:** [Relevant architectural patterns and constraints]
- **Technical Constraints:** [Limitations based on existing codebase]

**External Research:**
- **Industry Best Practices:** [Key findings from WebSearch validation]
- **Case Studies:** [Relevant examples from similar implementations]
- **Academic Research:** [Research papers or industry reports consulted]
- **Standards & Methodologies:** [Proven approaches identified]

**Cross-Reference Validation:**
- **Common Patterns:** [Recurring themes across multiple sources]
- **Anti-Patterns:** [Approaches to avoid based on research]
- **Validation Sources:** [List of sources used for cross-referencing]

### Analysis
**Solution Categories:**
1. **[Category Name]**
   - **Approach:** [Brief description]
   - **Evidence:** [Supporting research findings]
   - **Feasibility:** [High/Medium/Low with rationale]
   - **Risks:** [Potential challenges]

2. **[Category Name]**
   - **Approach:** [Brief description]
   - **Evidence:** [Supporting research findings]
   - **Feasibility:** [High/Medium/Low with rationale]
   - **Risks:** [Potential challenges]

[Add additional categories as needed]

**Comparative Analysis:**
- **Strengths/Weaknesses:** [Comparison matrix of approaches]
- **Resource Requirements:** [Development, design, testing needs]
- **Timeline Implications:** [Relative complexity and time estimates]

### Recommendations
**Primary Recommendation:** [Top approach with detailed justification]

**Alternative Options:** [Secondary approaches worth considering]

**Next Steps:** [Specific actions for feature proposal development]

**Research Gaps:** [Areas needing further investigation]

### Integration
**Feature Proposal Preparation:**
- **Selected Ideas:** [Ideas ready for proposal development]
- **Key Requirements:** [Initial requirements identified]
- **Stakeholder Considerations:** [Business and user impact factors]

**Command Transition:**
- **Ready for:** `/project:feature-proposal [selected idea]`
- **Required Inputs:** [What the next command needs from this output]
- **Success Handoff:** [Validation criteria for successful transition]

## Validation Checklist

Before completing brainstorm output, verify:
- [ ] All research sources are cited and validated
- [ ] At least 3 solution categories are explored
- [ ] Feasibility assessment is evidence-based
- [ ] Primary recommendation is clearly justified
- [ ] Integration section prepares for next command
- [ ] Research gaps are identified for future investigation

## File Output Instructions

Save this structured output using the Write tool with filename:
`brainstorm-[topic-keyword]-[YYYY-MM-DD].md`

Example: `brainstorm-user-auth-2024-07-03.md`

## Template Usage Notes

- Replace all bracketed placeholders with actual content
- Maintain the structure but adapt content length as needed
- Include links to external sources for validation
- Use bullet points for clarity and scannability
- Ensure each section flows logically to the next