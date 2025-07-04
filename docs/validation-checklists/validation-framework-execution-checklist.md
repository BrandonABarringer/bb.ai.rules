# Validation Framework Command Execution Checklist

**Purpose:** Ensure the validation-framework command applies systematic methodology correctly and produces reliable quality assessments.

**Command:** 06_validation-framework  
**Output Type:** Validation Report (Quality Assessment Documentation)  
**Expected Location:** docs/validation-reports/[command-name]-validation-report-[YYYY-MM-DD].md

## Pre-Execution Requirements

### Extended Thinking Mode Activation
- [ ] Extended thinking mode activated with validation reasoning documentation
- [ ] Systematic approach to validation methodology clearly documented
- [ ] Framework selection rationale explained in thinking section

### Module Access Documentation
- [ ] @docs/modules/thinking-mode.md accessed and documented
- [ ] @docs/modules/workflow-integration.md accessed for command relationship analysis
- [ ] @docs/validation-framework-guide.md accessed and applied systematically
- [ ] @docs/modules/output-structure.md accessed for report formatting

### Target Command Analysis
- [ ] Target command definition file read and analyzed (.claude/commands/[target].md)
- [ ] Command purpose and expected outputs clearly identified
- [ ] Command type classification performed (Documentation Generator vs Artifact Creator)
- [ ] Workflow position and integration points documented

## Framework Application Process

### Step 1: Command Type Classification
- [ ] Command categorized as Documentation Generator OR Artifact Creator
- [ ] Classification rationale provided with specific evidence
- [ ] Appropriate validation criteria selected based on command type
- [ ] Expected output locations identified for target command type

### Step 2: Complete Output Inventory
- [ ] ALL expected outputs systematically searched for and documented
- [ ] Glob tool used for comprehensive file discovery
- [ ] LS tool used for directory content analysis
- [ ] mcp__scopecraft__task_list used for task-creation validation (if applicable)
- [ ] Total expected vs found counts documented with specific numbers
- [ ] No sampling or cherry-picking - every output checked

### Step 3: Critical Empty Content Check
- [ ] Empty content check performed BEFORE quality assessment
- [ ] Read tool used to verify content completeness for each output
- [ ] Any empty sections, placeholder content, or stubs documented
- [ ] "Fail Fast on Empty Content" principle applied
- [ ] Automatic failure triggered if empty content found

### Step 4: Systematic Quality Assessment
- [ ] Quality metrics applied appropriate to command type
- [ ] EACH output individually assessed and scored
- [ ] Evidence provided for every quality claim made
- [ ] Specific examples and quotes included in assessment
- [ ] No vague statements or unsupported assertions

## Evidence Collection Requirements

### Quantitative Evidence
- [ ] Word counts provided for content-based assessments
- [ ] Item counts provided for checklist-based assessments
- [ ] File sizes and line counts documented where relevant
- [ ] Completion percentages calculated with specific ratios

### Qualitative Evidence
- [ ] Direct quotes from content provided as proof of quality claims
- [ ] Specific examples of good practices highlighted
- [ ] Specific examples of issues or gaps documented
- [ ] Screenshots or file excerpts included where helpful

### Framework Compliance Evidence
- [ ] Evidence provided that all four core principles were applied
- [ ] Documentation that red flags were actively avoided
- [ ] Proof that systematic approach was followed throughout
- [ ] Verification that no bias or sampling occurred

## Report Quality Standards

### Structure Compliance
- [ ] Template structure followed exactly with all required sections
- [ ] Executive summary provides clear assessment and score
- [ ] Systematic quality assessment section covers ALL outputs
- [ ] Evidence collection section provides concrete proof
- [ ] Framework compliance section confirms methodology

### Content Quality Standards
- [ ] Report provides actionable insights for command improvement
- [ ] Scoring rationale clearly explained with specific criteria
- [ ] Issues and recommendations are specific and implementable
- [ ] Assessment is honest and evidence-based, not promotional
- [ ] Framework principles visibly applied throughout validation

### Evidence Standards
- [ ] Every score and assessment claim backed by specific evidence
- [ ] No assertions made without concrete proof provided
- [ ] Quantitative metrics included where possible
- [ ] Qualitative examples support all major findings

## Red Flag Avoidance Verification

### Red Flags Successfully Avoided
- [ ] No statements like "All outputs validated" without listing each
- [ ] High scores (90+) include specific issues or gaps identified
- [ ] Specific content examples provided, not vague assessments
- [ ] No missing items in validation - every output checked
- [ ] No vague statements like "content looks good" without evidence

### Quality Indicators Present
- [ ] Systematic methodology clearly documented and followed
- [ ] Honest assessment including both strengths and weaknesses
- [ ] Evidence-based conclusions with specific supporting data
- [ ] Framework compliance demonstrated throughout process
- [ ] Actionable recommendations for improvement provided

## Scoring and Assessment Standards

### Scoring Criteria Applied
- [ ] Pass threshold of 85/100 applied consistently
- [ ] Scoring criteria appropriate to command type used
- [ ] Individual output scores aggregated properly
- [ ] Overall assessment reflects actual deliverable quality
- [ ] Framework compliance factored into final assessment

### Assessment Honesty
- [ ] Issues and gaps honestly reported and documented
- [ ] Strengths celebrated with specific evidence
- [ ] Score reflects genuine deliverable quality, not process compliance
- [ ] Recommendations are constructive and specific
- [ ] Overall assessment enables command improvement

## Output File Standards

### File Creation Requirements
- [ ] Report created using Write tool in correct location
- [ ] File naming follows convention: [command-name]-validation-report-[YYYY-MM-DD].md
- [ ] File location: docs/validation-reports/
- [ ] Content follows template structure exactly
- [ ] All bracketed placeholders replaced with actual content

### Content Completeness
- [ ] All required sections present and substantively completed
- [ ] Executive summary provides clear verdict and rationale
- [ ] Evidence collection demonstrates thorough validation
- [ ] Framework compliance confirmed with specific verification
- [ ] Recommendations provide clear path for improvement

## Framework Integrity Verification

### Core Principles Applied
- [ ] **Validate the Actual Output:** Focused on deliverables, not documentation about them
- [ ] **Check Everything:** No sampling bias, all outputs systematically verified
- [ ] **Fail Fast on Empty Content:** Empty content check performed first
- [ ] **Evidence-Based:** Concrete proof provided for all validation claims

### Systematic Approach Confirmed
- [ ] Methodology clearly documented and consistently applied
- [ ] No shortcuts or assumptions made in validation process
- [ ] Complete audit trail from discovery through assessment
- [ ] Framework guide principles visibly followed throughout

## Post-Execution Verification

### Report Quality Check
- [ ] Report provides genuine insight into command effectiveness
- [ ] Assessment enables improvement of target command
- [ ] Validation methodology can be replicated by others
- [ ] Framework compliance helps maintain quality standards
- [ ] Evidence collection supports all conclusions drawn

### Validation Framework Enhancement
- [ ] Any framework improvements identified and documented
- [ ] Lessons learned captured for future validations
- [ ] Methodology refinements suggested where applicable
- [ ] Framework effectiveness demonstrated through application

## Success Criteria

A successful validation-framework command execution should:
- Correctly classify the target command type with clear rationale
- Systematically inventory and assess ALL outputs produced
- Apply appropriate validation criteria based on command type
- Provide evidence-based assessment with concrete supporting data
- Generate actionable recommendations for command improvement
- Demonstrate framework compliance throughout the validation process
- Produce a comprehensive report that enables quality improvement

## Common Failure Modes to Avoid

- **Sampling Bias:** Only checking outputs known to be good
- **Documentation Focus:** Validating process compliance instead of deliverable quality
- **Cherry-Picking:** Selecting favorable examples while ignoring issues
- **Vague Assessment:** Making claims without providing specific evidence
- **Score Inflation:** Giving high scores without identifying areas for improvement
- **Framework Deviation:** Not following the systematic methodology consistently