# Validation Framework Command

## Purpose

Apply the systematic validation framework to assess command effectiveness by validating actual deliverables produced, not just documentation compliance. This command distinguishes between documentation generators and artifact creators to apply appropriate validation criteria.

## Usage

`/project:validation-framework [command-number-or-name]`

Examples:
- `/project:validation-framework 03`
- `/project:validation-framework feature-to-prd`
- `/project:validation-framework task-creation`

## Instructions

When this command is used, follow this structured validation workflow:

### 1. Enable Extended Thinking Mode
See @docs/modules/thinking-mode.md for extended thinking mode requirements.
**For this command:** Use Read tool to access module and document validation reasoning process.

### 2. Command Identification Phase
See @docs/modules/workflow-integration.md for command relationship analysis.
**For this command:** Use Read tool to access module and understand command context.

**Command Analysis (MANDATORY):**
- **Use Read tool for command definition:** Access .claude/commands/[target-command].md
- Identify command purpose, expected outputs, and workflow position
- Determine command type: Documentation Generator vs Artifact Creator
- Document command scope and validation requirements

### 3. Validation Framework Application
See @docs/validation-framework-guide.md for systematic validation methodology.
**For this command:** Use Read tool to access framework and apply systematically.

**Framework Selection (MANDATORY):**
- **Type 1 - Documentation Generators:** brainstorm, feature-proposal, feature-to-prd, feature-planning
  - Validation Focus: Document quality, completeness, template compliance
  - Output Location: docs/outputs/sessions/[date]/[workflow]/
- **Type 2 - Artifact Creators:** task-creation, code generators, config builders
  - Validation Focus: Deliverable completeness and immediate usability
  - Output Location: .tasks/, code files, configuration files

### 4. Systematic Output Inventory
**MANDATORY STEP 1:** Complete inventory of ALL outputs
- **Use Glob tool for output discovery:** Search for all files created by target command
- **Use LS tool for directory analysis:** List contents of expected output locations
- **Use mcp__scopecraft__task_list:** For task-creation command validation
- Document total expected vs found outputs with exact counts

### 5. Critical Empty Content Check
**MANDATORY STEP 2:** Validate no empty or stub content exists
- **Use Read tool for content verification:** Check each output file for completeness
- Apply "Fail Fast on Empty Content" principle from framework
- Document any empty sections, placeholder content, or stubs found
- **CRITICAL:** Any empty content = automatic validation failure

### 6. Systematic Quality Assessment
**MANDATORY STEP 3:** Apply appropriate validation criteria

**For Documentation Generators:**
- Verify file exists at expected path
- Check all template sections are populated
- Validate content quality (word count, specificity, integration preparation)
- Assess workflow integration readiness

**For Artifact Creators:**
- List ALL created artifacts with locations
- Check EACH artifact for completeness
- Verify immediate usability for developers
- Confirm no placeholder or generic content

### 7. Evidence-Based Scoring
**MANDATORY STEP 4:** Provide concrete evidence for all validation claims
- Include specific examples of content checked
- Provide quantitative metrics (word counts, item counts, etc.)
- Show samples of actual content as proof
- Document any issues or gaps discovered

### 8. Comprehensive Validation Report
See @docs/modules/output-structure.md for report formatting requirements.
**For this command:** Use Write tool to create systematic validation report.

**MANDATORY REPORT STRUCTURE:**
```markdown
# [Command Name] Validation Report

**Date:** [YYYY-MM-DD]
**Command:** [command-name]
**Validation Type:** [Documentation Generator / Artifact Creator]

## Executive Summary
**Result:** PASS/FAIL - [Score]/100
**Command Type:** [Type with rationale]
**Assessment:** [Brief quality assessment]

## Outputs Inventory
**Total Expected:** [N]
**Found:** [N]
**Missing:** [List any missing outputs]

## Empty Content Check
**Result:** PASS/FAIL
**Empty Items Found:** [List with specific sections/files]

## Systematic Quality Assessment
[For EACH output, provide:]
### [Output Name/ID]
**Exists:** Yes/No
**Empty Sections:** None/[List sections]
**Quality Metrics:**
- [Metric 1]: [Value] (Pass/Fail)
- [Metric 2]: [Value] (Pass/Fail)
**Evidence:** [Specific examples]
**Score:** __/100

## Overall Results
**Total Score:** __/100
**Pass/Fail:** [Result based on 85+ threshold]
**Critical Issues:** [List any blocking issues]

## Recommendations
[Specific improvements needed]
```

### 9. Framework Compliance Verification
**CRITICAL VALIDATION REQUIREMENTS:**
- All four core principles applied (Validate Actual Output, Check Everything, Fail Fast, Evidence-Based)
- No red flags present (vague statements, missing items, high scores without issues)
- Complete evidence provided for all claims
- Systematic approach documented throughout

### 10. Final Validation Report Output
**MANDATORY OUTPUT REQUIREMENTS:**
- Use Write tool to create report in docs/validation-reports/
- File naming: [command-name]-validation-report-[YYYY-MM-DD].md
- Include validation framework compliance confirmation
- Document framework application methodology used

## Expected Outcome

- Comprehensive validation report with systematic assessment
- Clear identification of command type and appropriate criteria applied
- Complete inventory of ALL outputs produced by target command
- Evidence-based scoring with specific examples and metrics
- **CRITICAL:** Honest assessment focusing on deliverable quality
- **CRITICAL:** Framework compliance demonstrated throughout process
- **CRITICAL:** No sampling bias or cherry-picking in validation

## Arguments

**Required:** Command number (01-05) or command name to validate
- `01` or `brainstorm`
- `02` or `feature-proposal`
- `03` or `feature-to-prd`
- `04` or `feature-planning`
- `05` or `task-creation`

## Example Usage

```bash
# Validate Command 03 using framework
/project:validation-framework 03

# Validate task-creation command
/project:validation-framework task-creation

# Validate feature proposal command
/project:validation-framework feature-proposal
```

## Integration Notes

This is a quality assurance command that validates the effectiveness of other workflow commands. It should be used:
- After implementing new commands
- For regular quality audits
- When validation discrepancies are discovered
- To ensure framework compliance across all commands

## Framework Principles Applied

1. **Validate the Actual Output** - Checks what commands produce, not what they claim
2. **Check Everything** - No sampling, systematic verification of ALL deliverables
3. **Fail Fast on Empty Content** - Immediate failure for empty/stub content
4. **Evidence-Based** - Concrete proof required for all validation claims

## Success Criteria

- Command type correctly identified with rationale
- All outputs systematically inventoried and checked
- Empty content check performed before quality assessment
- Evidence provided for every validation claim
- Framework red flags avoided (no vague statements, missing items, etc.)
- Honest scoring focused on actual deliverable usability