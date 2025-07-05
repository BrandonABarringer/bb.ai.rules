# Update thinking-mode module with reasoning patterns

---
type: feature
status: todo
area: prompt-engineering
---


## Instruction
Update the thinking-mode module to incorporate the new reasoning patterns from Phase 1: Chain-of-Thought, Step-Back Prompting, and Self-Ask techniques.

The thinking-mode module is central to all commands and currently provides basic extended thinking activation. This task enhances it with structured reasoning patterns that all commands can leverage for improved analytical quality.

## Context
The current thinking-mode module activates visible reasoning but doesn't provide structured patterns for different types of analytical tasks. By incorporating the three core techniques from Phase 1, we create a unified reasoning framework that ensures consistency across all commands.

## Current State
The existing module at `docs/modules/thinking-mode.md` provides:
- Basic extended thinking activation instructions
- General guidance for documenting thought processes
- Integration points with other modules

## Target State
Enhanced module that provides:
- Structured Chain-of-Thought patterns for step-by-step reasoning
- Step-Back Prompting templates for conceptual foundation
- Self-Ask question generation frameworks
- Clear guidance on when and how to use each pattern
- Examples of effective reasoning chains

## Tasks
- [ ] Review current thinking-mode.md module structure and content
- [ ] Design section for Chain-of-Thought reasoning patterns with examples
- [ ] Create templates for different CoT scenarios (analysis, synthesis, evaluation)
- [ ] Design section for Step-Back Prompting with trigger conditions
- [ ] Create conceptual exploration templates for different domains
- [ ] Design section for Self-Ask patterns with question generation guides
- [ ] Create question chain templates for validation and completeness
- [ ] Integrate all three techniques into cohesive reasoning framework
- [ ] Add decision tree for selecting appropriate reasoning pattern
- [ ] Include examples from each command showing proper usage
- [ ] Create quick reference guide for reasoning pattern selection
- [ ] Validate module provides clear, actionable guidance

## Deliverable
Enhanced thinking-mode.md module that serves as the central reasoning pattern reference for all commands:

**Module Structure:**
1. **Overview** - Unified reasoning framework introduction
2. **Chain-of-Thought Patterns**
   - When to use: Complex analysis, multi-step processes
   - Pattern templates for different scenarios
   - Examples from Commands 02-03
3. **Step-Back Prompting**
   - When to use: Conceptual foundation, avoiding tunnel vision
   - Exploration templates and triggers
   - Examples from Commands 01, 04
4. **Self-Ask Techniques**
   - When to use: Validation, completeness checking
   - Question generation frameworks
   - Examples from Commands 05-06
5. **Pattern Selection Guide**
   - Decision tree for choosing techniques
   - Combination strategies
6. **Integration Examples**
   - How commands leverage the patterns
   - Best practices

**Quality Criteria:**
- Module provides immediately actionable patterns
- Clear guidance on when to use each technique
- Templates are adaptable to different contexts
- Examples demonstrate effective usage
- Seamless integration with existing module structure

**Files to be delivered:**
- `docs/modules/thinking-mode.md` (enhanced version)
- Migration guide for updating commands to use new patterns

## Log
