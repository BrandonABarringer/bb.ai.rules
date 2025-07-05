# Integrate Self-Ask patterns across Commands 05-06

---
type: feature
status: todo
area: prompt-engineering
---


## Instruction
Integrate Self-Ask prompting patterns across Commands 05 (Task Creation) and 06 (Validation Framework) to enhance completeness validation and systematic quality assessment.

Self-Ask prompting enables the AI to generate and answer its own follow-up questions, leading to more comprehensive analysis and reduced blind spots. This technique is particularly valuable for quality assurance and completeness checking.

## Context
Commands 05 and 06 are critical quality gates in the workflow. Command 05 creates developer-ready tasks that must be complete and actionable. Command 06 validates output quality across all commands. Both would benefit from systematic self-questioning to ensure nothing is overlooked.

## Research Foundation
Based on the Prompt Report analysis, Self-Ask prompting:
- Improves completeness by 35-45% through systematic questioning
- Identifies gaps and edge cases that direct analysis might miss
- Enhances validation thoroughness and reliability
- Particularly effective for quality assurance and review processes

## Implementation Approach
Enhance both commands with Self-Ask patterns that systematically generate questions about completeness, quality, and potential issues. This creates a more rigorous validation process while maintaining efficiency.

## Tasks
- [ ] Analyze Command 05 (Task Creation) validation requirements and quality standards
- [ ] Design Self-Ask patterns for task completeness (context sufficiency → actionability → clarity → measurability)
- [ ] Implement Self-Ask validation phase before task finalization
- [ ] Create question generation prompts for developer readiness assessment
- [ ] Test enhanced Command 05 with various task complexity levels
- [ ] Analyze Command 06 (Validation Framework) assessment methodology
- [ ] Design Self-Ask patterns for validation thoroughness (coverage → evidence → edge cases → failure modes)
- [ ] Implement Self-Ask questioning throughout validation process
- [ ] Create systematic question chains for different command types
- [ ] Test enhanced Command 06 across all command validation scenarios
- [ ] Document Self-Ask patterns and question generation guidelines
- [ ] Measure improvement in completeness and quality detection rates

## Deliverable
Enhanced versions of Commands 05 and 06 with integrated Self-Ask prompting that:

**Command 05 Enhancements:**
- Self-generated questions about task completeness
- Systematic validation of developer readiness
- Edge case identification for task execution
- Gap detection in instruction, tasks, and deliverables

**Command 06 Enhancements:**
- Comprehensive question generation for validation coverage
- Systematic probing of potential quality issues
- Evidence sufficiency questioning
- Failure mode and edge case exploration

**Quality Criteria:**
- Self-Ask patterns generate relevant, insightful questions
- Questions lead to actionable improvements or validations
- No significant gaps remain after Self-Ask process
- Enhanced commands catch more quality issues
- Validation becomes more systematic and repeatable

**Files to be delivered:**
- `.claude/commands/05_task-creation.md` (enhanced)
- `.claude/commands/06_validation-framework.md` (enhanced)
- `docs/modules/self-ask-validation.md` (new)
- Examples of Self-Ask improving quality detection

## Log
