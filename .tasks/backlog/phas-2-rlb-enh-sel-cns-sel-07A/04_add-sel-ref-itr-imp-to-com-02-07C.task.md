# Add Self-Refine iterative improvement to Commands 02-04

---
type: feature
status: todo
area: prompt-engineering
---


## Instruction
Add Self-Refine iterative improvement capabilities to Commands 02-04 (Feature Proposal, Feature to PRD, Feature Planning) to enhance output quality through systematic self-critique and refinement loops.

Self-Refine is a powerful self-criticism technique where the AI generates an initial output, critiques it systematically, then produces an improved version. This iterative process continues until quality criteria are met or improvements plateau.

## Context
Commands 02-04 currently generate outputs in a single pass. While structured, they miss opportunities for:
- Identifying gaps and weaknesses post-generation
- Strengthening arguments with additional evidence
- Improving clarity and coherence
- Catching inconsistencies or contradictions
- Enhancing completeness and depth

## Research Foundation
Based on the Prompt Report, Self-Refine:
- Improves output quality by 30-50% through iteration
- Catches 70%+ more errors and gaps than single-pass
- Enhances coherence and logical flow significantly
- Particularly effective for complex analytical documents
- Works synergistically with Self-Consistency

## Implementation Approach
Enhance Commands 02-04 with a 3-iteration Self-Refine loop:
1. Initial generation using enhanced reasoning
2. Systematic critique identifying improvements
3. Refined version addressing critiques
4. Final quality assessment and polish

## Tasks
- [ ] Design Self-Refine framework compatible with existing command structure
- [ ] Create critique templates for feature proposals (completeness, feasibility, clarity)
- [ ] Create critique templates for PRDs (specifications, stakeholders, measurability)
- [ ] Create critique templates for project plans (realism, risks, dependencies)
- [ ] Implement iterative refinement loop with quality scoring
- [ ] Design improvement tracking to show evolution across iterations
- [ ] Build stopping criteria based on quality score plateau
- [ ] Integrate Self-Refine with Self-Consistency synthesis points
- [ ] Add refinement documentation showing critique rationale
- [ ] Create visual diff showing improvements between iterations
- [ ] Test refinement effectiveness across 15 documents (5 per command)
- [ ] Measure quality score improvements per iteration
- [ ] Optimize iteration count for quality vs. performance balance
- [ ] Document Self-Refine patterns and best practices

## Deliverable
Commands 02-04 enhanced with Self-Refine iterative improvement:

**Core Implementation:**
1. **Refinement Framework**
   - Initial generation with full reasoning
   - Systematic critique generation
   - Targeted improvements based on critique
   - Quality scoring and iteration control

2. **Command-Specific Critiques**
   - **Command 02**: Feasibility depth, user story quality, evidence strength
   - **Command 03**: Specification completeness, stakeholder coverage, metrics
   - **Command 04**: Timeline realism, risk identification, resource accuracy

3. **Output Enhancements**
   - Refinement history documentation
   - Quality score progression
   - Key improvements highlighted
   - Final quality certification

**Quality Criteria:**
- 30%+ quality improvement from initial to final
- All major gaps identified and addressed
- Logical coherence validated
- No contradictions remain
- Professional polish achieved
- 3 iterations maximum for efficiency

**Files to be delivered:**
- `.claude/commands/02_feature-proposal.md` (Self-Refine added)
- `.claude/commands/03_feature-to-prd.md` (Self-Refine added)
- `.claude/commands/04_feature-planning.md` (Self-Refine added)
- `docs/modules/self-refine-patterns.md` (new)
- Test results showing iterative quality improvements
- Best practices guide for refinement loops

## Log
