# Add Step-Back Prompting to Commands 01 & 04

---
type: feature
status: todo
area: prompt-engineering
---


## Instruction
Implement Step-Back Prompting techniques in Commands 01 (Brainstorm) and 04 (Feature Planning) to establish stronger conceptual foundations before diving into specific details.

Step-Back Prompting is a technique where the AI first considers higher-level concepts and principles before addressing specific questions. This approach significantly improves reasoning quality by ensuring proper context and avoiding premature focus on details.

## Context
Commands 01 and 04 currently jump directly into specific research and planning activities without establishing conceptual foundations. This can lead to missing important contextual factors, overlooking alternative approaches, and building on unvalidated assumptions.

## Research Foundation
Based on the Prompt Report analysis, Step-Back Prompting:
- Improves problem-solving accuracy by 30-40% on complex tasks
- Reduces tunnel vision and premature convergence on solutions
- Enhances consideration of broader context and constraints
- Particularly effective for creative ideation and strategic planning

## Implementation Approach
Enhance both commands with explicit step-back phases that establish conceptual understanding before proceeding to specific analysis. This maintains compatibility while adding depth to the analytical process.

## Tasks
- [ ] Analyze Command 01 (Brainstorm) to identify where step-back prompting would add value
- [ ] Design step-back patterns for brainstorming (problem space → fundamental principles → constraints → opportunities)
- [ ] Implement step-back phase at the beginning of Command 01 research workflow
- [ ] Create prompts for conceptual exploration before specific idea generation
- [ ] Test enhanced Command 01 with complex brainstorming scenarios
- [ ] Analyze Command 04 (Feature Planning) to identify step-back opportunities
- [ ] Design step-back patterns for planning (project context → architectural principles → resource constraints → risk factors)
- [ ] Implement step-back phase before detailed project breakdown
- [ ] Create prompts for strategic consideration before tactical planning
- [ ] Test enhanced Command 04 with complex feature planning scenarios
- [ ] Document step-back prompting patterns in module documentation
- [ ] Validate improved conceptual foundation quality in outputs

## Deliverable
Enhanced versions of Commands 01 and 04 with integrated Step-Back Prompting that:

**Command 01 Enhancements:**
- Conceptual exploration phase before specific research
- Problem space analysis establishing fundamental understanding
- Constraint and opportunity mapping at high level
- Foundation for more innovative and comprehensive ideation

**Command 04 Enhancements:**
- Strategic context establishment before tactical planning
- Architectural principle consideration upfront
- Resource and risk landscape understanding
- Foundation for more robust project plans

**Quality Criteria:**
- Step-back phases produce clear conceptual frameworks
- Subsequent detailed work builds on established foundations
- Output shows improved consideration of broader context
- No tunnel vision or premature solution convergence
- Enhanced commands maintain workflow compatibility

**Files to be delivered:**
- `.claude/commands/01_brainstorm.md` (enhanced)
- `.claude/commands/04_feature-planning.md` (enhanced)
- `docs/modules/step-back-prompting.md` (new)
- Examples demonstrating improved conceptual foundation quality

## Log
