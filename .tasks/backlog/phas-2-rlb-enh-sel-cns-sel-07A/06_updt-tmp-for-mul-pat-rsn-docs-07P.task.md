# Update templates for multi-path reasoning documentation

---
type: feature
status: todo
area: prompt-engineering
---


## Instruction
Update all command output templates to incorporate multi-path reasoning documentation from Self-Consistency, refinement history from Self-Refine, and multi-verifier validation results from DiVeRSe.

Phase 2's reliability enhancements generate rich analytical data through multiple reasoning paths, iterative refinements, and comprehensive validation. Templates must elegantly capture this complexity while maintaining readability and usability.

## Context
Current templates (updated in Phase 1) capture single-path reasoning but need enhancement for:
- Multiple reasoning paths and their synthesis
- Iterative refinement history and improvements
- Multi-verifier validation results
- Confidence scores and divergence indicators
- Visual representations of consensus/divergence

## Requirements
Each template needs structured sections for:
- Self-Consistency: Path documentation, synthesis results, confidence scores
- Self-Refine: Iteration history, improvements made, quality progression
- DiVeRSe: Multi-verifier results, consensus findings, priority issues

## Design Principles
- Progressive disclosure: Summary first, details on demand
- Visual clarity: Use formatting to highlight key information
- Actionable insights: Focus on decisions and improvements
- Backward compatibility: Graceful degradation for single-path mode

## Tasks
- [ ] Analyze Phase 1 template updates and identify integration points
- [ ] Design multi-path section for feature-proposal-output-template.md
- [ ] Add synthesis visualization for reasoning path convergence
- [ ] Design refinement history section showing iteration improvements
- [ ] Create quality score progression visualization
- [ ] Update feature-to-prd-output-template.md with stakeholder path synthesis
- [ ] Add confidence indicators for requirement specifications
- [ ] Update feature-planning-output-template.md with three-point estimates
- [ ] Design risk synthesis section from planning path divergence
- [ ] Update validation-framework-output-template.md for multi-verifier results
- [ ] Create verifier consensus dashboard layout
- [ ] Design progressive disclosure mechanisms for detailed data
- [ ] Add visual indicators for confidence and divergence
- [ ] Create template usage guide for Phase 2 features
- [ ] Test templates with sample outputs showing all enhancements

## Deliverable
Enhanced output templates capturing Phase 2 reliability features:

**Template Enhancements:**

1. **feature-proposal-output-template.md**
   - Multi-Path Analysis section with 3 perspectives
   - Synthesis Results with consensus/divergence
   - Refinement History showing improvements
   - Confidence Scores for key decisions

2. **feature-to-prd-output-template.md**
   - Stakeholder Path Synthesis matrix
   - Requirement Confidence indicators
   - Specification Refinement trail
   - Multi-verifier validation summary

3. **feature-planning-output-template.md**
   - Three-Point Estimates visualization
   - Risk Synthesis from path divergence
   - Planning Refinement history
   - Critical Path confidence levels

4. **validation-framework-output-template.md**
   - Five-Verifier results dashboard
   - Consensus findings highlight
   - Issue prioritization matrix
   - Confidence intervals for scores

**Quality Criteria:**
- Templates remain readable despite additional data
- Progressive disclosure works smoothly
- Visual elements enhance understanding
- Backward compatibility maintained
- Key insights prominently displayed
- Details accessible but not overwhelming

**Files to be delivered:**
- All 4 enhanced template files with Phase 2 sections
- `docs/templates/multi-path-documentation-guide.md` (new)
- Visual design specifications for new elements
- Sample outputs demonstrating all features

## Log
