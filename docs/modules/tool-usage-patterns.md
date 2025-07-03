# Tool Usage Patterns Module

## Standard Tool Usage Instructions

### Codebase Analysis Tools
**Use `Grep` tool to:**
- Search for related implementations and patterns
- Find existing similar features or functions
- Identify current architecture approaches
- Locate relevant code sections for analysis

**Use `Glob` tool to:**
- Identify relevant files by pattern matching
- Find files related to specific features or components
- Locate configuration files and documentation
- Discover project structure and organization

**Use `Read` tool to:**
- Analyze current architecture and patterns
- Review existing documentation and specifications
- Access previous command outputs for integration
- Examine specific files for implementation details

### Research and Validation Tools
**Use `WebSearch` tool to:**
- Find case studies and industry best practices
- Research academic papers and industry reports
- Analyze competitor solutions and market approaches
- Look for proven methodologies and standards
- Validate approaches against real-world implementations

### Output Creation Tools
**Use `Write` tool to:**
- Save structured outputs with standardized filenames
- Create documentation following template requirements
- Generate reports with consistent formatting
- Output results to designated directory structures

### Integration and Reference Tools
**Use file references with `@` prefix:**
- Include template structures: `@docs/templates/[template-name].md`
- Reference modular components: `@docs/modules/[module-name].md`
- Access previous outputs: `@docs/outputs/sessions/[path]/[filename].md`

## Tool Combination Patterns

### Research Validation Sequence

**Systematic Baseline Approach (Recommended for consistency):**
1. **Codebase Analysis:** Grep (1 call) → Glob (1 call) → Read (1 call)
2. **External Research:** WebSearch (1 call) → Cross-reference validation
3. **Integration:** Read previous outputs → Synthesize findings

**Natural Research Approach (For complex analysis):**
1. **Iterative Codebase Analysis:** Multiple Grep/Glob/Read cycles following research leads
2. **Deep External Research:** Multiple WebSearch queries exploring different angles
3. **Comprehensive Integration:** Extensive cross-validation across all sources

**Hybrid Approach (Best of both):**
- **Phase 1:** Execute systematic baseline (1 of each tool) for guaranteed coverage
- **Phase 2:** Follow research leads with additional targeted tool calls as needed
- **Phase 3:** Document rationale for additional research beyond baseline

### Output Creation Sequence
1. **Template Access:** Read template structure
2. **Content Generation:** Follow template format
3. **File Output:** Write to designated directory structure
4. **Validation:** Confirm template compliance

## Usage in Commands

Reference this module in command instructions with:
```markdown
See @docs/modules/tool-usage-patterns.md for standard tool usage requirements.
```

## Tool Usage Documentation Requirements

### Mandatory Documentation Pattern
For complex commands requiring validation, document each tool use:

```markdown
**Tool Usage Log:**
- [Tool Name] used for [specific purpose]: [brief description of what was found/accomplished]
- Example: "Grep tool used for existing authentication patterns: Found 3 OAuth implementations in auth/ directory"
- Example: "WebSearch tool used for MLOps CLI validation: Confirmed ZenML and MLflow as leading frameworks"
```

### Documentation Timing
- **During Thinking Mode:** Log tool usage as you perform it
- **In Output:** Include summary of all tools used and their contributions
- **For Validation:** Reference specific tool outputs in feasibility assessments

## Best Practices

- **Always specify tools explicitly** in command instructions
- **Use tools in logical sequences** for comprehensive analysis
- **Reference files with full paths** for clarity and consistency
- **Validate tool outputs** before proceeding to next steps
- **Document tool usage rationale** in thinking mode sections
- **Log contribution analysis** for each tool use in complex commands