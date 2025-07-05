# Update templates for enhanced reasoning documentation

---
type: feature
status: todo
area: prompt-engineering
---


## Instruction
Update all command output templates to include sections for enhanced reasoning documentation, ensuring the new Chain-of-Thought, Step-Back, and Self-Ask patterns are properly captured in deliverables.

The output templates define the structure of command deliverables. They must be enhanced to capture the reasoning processes introduced in Phase 1 while maintaining backward compatibility with existing outputs.

## Context
Current templates focus on final outputs without capturing the reasoning journey. With enhanced reasoning patterns, we need to document not just conclusions but also the analytical paths, conceptual foundations, and validation questions that led to those conclusions.

## Current State
Existing templates in `docs/templates/` include:
- brainstorm-output-template.md
- feature-proposal-output-template.md 
- feature-to-prd-output-template.md
- feature-planning-output-template.md
- task-creation-scopecraft-output-template.md
- validation-framework-output-template.md

## Enhancement Requirements
Each template needs new sections or enhanced existing sections to capture:
- Chain-of-Thought reasoning chains for key decisions
- Step-Back conceptual foundations where applicable
- Self-Ask validation questions and answers
- Reasoning transparency without overwhelming the reader

## Tasks
- [ ] Analyze brainstorm-output-template.md and add Step-Back conceptual foundation section
- [ ] Enhance feature-proposal-output-template.md with Chain-of-Thought decision trails
- [ ] Update feature-to-prd-output-template.md to include reasoning for stakeholder analysis
- [ ] Enhance feature-planning-output-template.md with strategic reasoning documentation
- [ ] Add Self-Ask validation section to task-creation-scopecraft-output-template.md
- [ ] Enhance validation-framework-output-template.md with systematic questioning trails
- [ ] Design consistent reasoning documentation format across all templates
- [ ] Create guidelines for when to include detailed reasoning vs. summary
- [ ] Add examples of well-documented reasoning in each template
- [ ] Ensure templates maintain readability despite additional content
- [ ] Create template usage guide highlighting new reasoning sections
- [ ] Validate enhanced templates with sample outputs from each command

## Deliverable
Enhanced output templates that elegantly capture reasoning processes while maintaining clarity and usability:

**Template Enhancements:**

1. **brainstorm-output-template.md**
   - New: "Conceptual Foundation" section (Step-Back results)
   - Enhanced: "Analysis Process" with reasoning chains
   
2. **feature-proposal-output-template.md**
   - New: "Decision Reasoning" subsections for key choices
   - Enhanced: "Feasibility Analysis" with CoT trails
   
3. **feature-to-prd-output-template.md**
   - New: "Stakeholder Analysis Reasoning" section
   - Enhanced: "Technical Decisions" with step-by-step logic
   
4. **feature-planning-output-template.md**
   - New: "Strategic Foundation" section (Step-Back)
   - Enhanced: "Risk Analysis" with reasoning chains
   
5. **task-creation-scopecraft-output-template.md**
   - New: "Completeness Validation" section (Self-Ask)
   - Enhanced: "Quality Assurance" with question trails
   
6. **validation-framework-output-template.md**
   - New: "Validation Questions" section throughout
   - Enhanced: All sections with reasoning transparency

**Quality Criteria:**
- Reasoning sections add value without cluttering output
- Templates guide users to include reasoning naturally
- Backward compatibility maintained
- Clear examples demonstrate proper usage
- Consistent format across all templates

**Files to be delivered:**
- All 6 enhanced template files in `docs/templates/`
- `docs/templates/reasoning-documentation-guide.md` (new)
- Example outputs showing enhanced reasoning capture

## Log
