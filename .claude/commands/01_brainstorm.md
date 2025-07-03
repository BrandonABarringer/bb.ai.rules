# Brainstorm Command

## Purpose

Generate evidence-based ideas for features, improvements, or solutions through comprehensive research validation.

## Usage

`/project:brainstorm [topic or problem description]`

## Instructions

When this command is used, follow this structured workflow:

### 1. Enable Extended Thinking Mode
See @docs/modules/thinking-mode.md for extended thinking mode requirements.
**For this command:** Activate visible reasoning and document exploration process.

**CRITICAL: Activate Extended Thinking Mode immediately:**
- Use clear section headings: "# Extended Thinking Mode: [Topic]"
- Expose your reasoning process and exploration
- Show how you're approaching the problem from multiple angles
- Document your thought process as you research and generate ideas
- Make decision-making transparent for complex analysis

### 2. Research Validation Phase
See @docs/modules/tool-usage-patterns.md for standard tool usage requirements.
**For this command:** Execute systematic research with flexible follow-up based on findings.

**MANDATORY: Execute hybrid research validation approach:**

**Phase 1: Systematic Baseline Research (Required)**
Execute exactly one tool call of each type in this sequence:
1. **Use Grep tool for codebase analysis:** Search for related implementations, patterns, existing features using core keywords from $ARGUMENTS
2. **Use Glob tool for file discovery:** Find files by pattern matching, locate relevant files, discover project structure  
3. **Use Read tool for architecture analysis:** Analyze current architecture, review existing documentation, examine most relevant file
4. **Use WebSearch tool for external validation:** Find industry best practices, case studies, academic research, standards & methodologies

**Phase 2: Follow-up Research (If Needed)**
Based on Phase 1 findings, conduct additional targeted research:
- Additional Grep/Glob searches for specific patterns discovered
- Read additional files that emerged as critical
- Additional WebSearch for specific technologies or approaches identified
- Document rationale for each additional tool call

**Phase 3: Cross-Reference Validation**
- Compare findings across multiple sources from both phases
- Identify common patterns and anti-patterns
- Validate approaches against real-world implementations

### 3. Idea Generation Process
- Generate diverse solution approaches based on research
- Consider multiple perspectives: technical, business, user experience
- Explore both conventional and innovative possibilities
- Evaluate feasibility within current constraints

### 4. Evidence-Based Analysis
- Support each idea with research findings
- Reference specific examples, case studies, or implementations
- Highlight lessons learned from similar solutions
- Identify potential risks and mitigation strategies

### 5. Structured Presentation
See @docs/modules/template-integration.md for template usage requirements.
See @docs/modules/output-structure.md for output organization requirements.
**For this command:** Follow brainstorm template structure with research-focused validation.

### 6. Workflow Integration
See @docs/modules/workflow-integration.md for command chaining requirements.
**For this command:** Prepare Integration section for feature-proposal handoff.

**MANDATORY: Execute Enhanced Directory Validation Process:**

**Step 6a: Topic Extraction from $ARGUMENTS**
1. Take first 2-3 meaningful words from arguments
2. Convert to lowercase
3. Replace spaces with hyphens
4. Remove special characters
5. Document the extraction process and result

**Step 6b: Directory Validation Process**
1. Use LS tool to check: `docs/outputs/sessions/[YYYY-MM-DD]/`
2. Parse existing workflow-XX directories
3. Determine next sequential workflow number
4. Create directory: `docs/outputs/sessions/[YYYY-MM-DD]/workflow-[NN]-[topic]/`
5. Document workflow numbering decision

**Step 6c: Template and Output Creation**
1. Read template: `@docs/templates/brainstorm-output-template.md`
2. Follow template structure exactly
3. Use Write tool with filename: `brainstorm-[topic]-[YYYY-MM-DD].md`
4. Ensure Integration section prepares for `/project:feature-proposal [topic]`

## Expected Outcome

- Visible thinking process throughout exploration
- Comprehensive research validation from multiple sources
- Evidence-based solution approaches with supporting rationale
- Structured presentation ready for feature proposal development
- Clear recommendations for next steps in the workflow

## Arguments

Use `$ARGUMENTS` to pass the topic or problem description for brainstorming.

## Example Usage

```
/project:brainstorm user authentication system for mobile app
/project:brainstorm improving API response times for large datasets
/project:brainstorm redesigning onboarding flow based on user feedback
```

## Integration Notes

This command is the first step in the idea-to-task workflow:
`brainstorm � feature-proposal � feature-to-prd � feature-planning � task-creation`

Results from this command should inform and structure the next phase of development planning.