# Validation Framework Guide

## Purpose

This guide ensures validation actually checks the deliverables produced by commands, not just documentation about them.

## Core Principles

1. **Validate the Actual Output** - Check what the command produces, not what it says it produces
2. **Check Everything** - No sampling, no cherry-picking, check ALL deliverables
3. **Fail Fast on Empty Content** - Any empty/stub content = automatic failure
4. **Evidence-Based** - Show proof of what was checked, not just scores

## Command Types and Validation Approaches

### Type 1: Documentation Generators
**Commands:** brainstorm, feature-proposal, feature-to-prd, feature-planning  
**Output:** Markdown documentation files  
**Validation Focus:** Document quality, completeness, template compliance

**Validation Steps:**
1. Verify file exists at expected path
2. Check all template sections are populated
3. Validate content quality (word count, specificity, etc.)
4. Ensure integration sections prepare for next command

### Type 2: Task/Artifact Creators  
**Commands:** task-creation, future code generators  
**Output:** Actual deliverables (Scopecraft tasks, code files, configs)  
**Validation Focus:** Deliverable completeness and usability

**Validation Steps:**
1. List ALL created artifacts
2. Check EACH artifact for completeness
3. Verify no empty/stub content exists
4. Confirm artifacts are immediately usable

## Systematic Validation Process

### Step 1: Inventory All Outputs
```bash
# For documentation commands
ls docs/outputs/sessions/[date]/[workflow]/

# For task creation
mcp__scopecraft__task_list
# or
ls -la .tasks/[location]/
```

### Step 2: Empty Content Check (CRITICAL)
Before any quality scoring, check for empty content:

```python
for each output:
    if has_empty_sections():
        return FAIL
```

### Step 3: Systematic Quality Check
Create a checklist that MUST be filled for each item:

```markdown
## Validation Checklist

### Item 1: [Name/ID]
- [ ] Exists at expected location
- [ ] All required sections present
- [ ] No empty sections
- [ ] Content meets minimum requirements
- [ ] Score: __/100

### Item 2: [Name/ID]
[Repeat for ALL items]
```

### Step 4: Evidence Collection
For each validation claim, provide evidence:

```markdown
**Claim:** Task has 250+ word instruction
**Evidence:** Word count = 276
**Sample:** "Design and implement the database schema..."
```

## Red Flags in Validation

These indicate flawed validation:

1. **"All tasks validated"** without listing each task
2. **High scores (90+)** without mentioning any issues
3. **No specific examples** of content being checked
4. **Missing items** in validation (e.g., only checking 4 of 6 tasks)
5. **Vague statements** like "content looks good"

## Validation Report Template

```markdown
# [Command] Validation Report

## Outputs Inventory
**Total Expected:** [N]
**Found:** [N]
**Missing:** [List any missing]

## Empty Content Check
**Result:** PASS/FAIL
**Empty Items Found:** [List with IDs]

## Systematic Quality Assessment

### [Output 1 ID/Name]
**Exists:** Yes/No
**Empty Sections:** None/[List sections]
**Quality Metrics:**
- [Metric 1]: [Value] (Pass/Fail)
- [Metric 2]: [Value] (Pass/Fail)
**Score:** __/100

[Repeat for EVERY output]

## Overall Results
**Total Score:** __/100
**Pass/Fail:** [Result]
**Critical Issues:** [List any]
```

## Automated Validation Helper

For commands that create multiple artifacts, use systematic checking:

```python
# Pseudo-code for validation
def validate_all_outputs(output_list):
    results = []
    for output in output_list:
        result = {
            'id': output.id,
            'exists': check_exists(output),
            'empty_sections': find_empty_sections(output),
            'quality_score': assess_quality(output),
            'issues': []
        }
        results.append(result)
    
    # Force validation of ALL items
    assert len(results) == len(output_list), "Not all outputs validated!"
    return results
```

## Common Validation Mistakes to Avoid

1. **Sampling Bias:** Only checking the "good" examples
2. **Confirmation Bias:** Looking for evidence of success, ignoring failures  
3. **Summary Without Detail:** High-level scores without item-by-item validation
4. **Missing Failures:** Not reporting empty/missing content
5. **Wrong Metrics:** Checking format when you should check completeness

## Conclusion

Proper validation requires:
- Checking EVERY deliverable systematically
- Failing fast on empty content
- Providing evidence for all claims
- Focusing on actual outputs, not documentation
- Being honest about failures and gaps

Remember: The goal is to ensure deliverables are actually useful, not to achieve high scores.