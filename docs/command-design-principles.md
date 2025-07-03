# Command Design Principles

## Purpose

This document explains the design rationale for different validation levels and requirements across workflow commands, ensuring consistency while respecting command-specific purposes.

## Standardized Elements

All commands follow these consistent patterns to prevent agent confusion:

### 1. Module Reference Pattern
```markdown
See @docs/modules/[module-name].md for [specific guidance type].
**For this command:** [Specific application instructions for this command]
```

**Rationale:** Consistent reference style with command-specific clarification prevents confusion about requirements.

### 2. Tool Usage Language Pattern
```markdown
**Use [Tool] for [purpose]:** [Specific requirements and expectations]
```

**Rationale:** Uniform instruction format while allowing different rigor levels for different command purposes.

### 3. Integration Section Format
```markdown
**Command Transition:**
- **Ready for:** `/project:[next-command] [parameters]`
- **Required Inputs:** [What the next command needs from this output]
- **Success Handoff:** [Validation criteria for successful transition]
```

**Rationale:** Standardized handoff preparation ensures smooth workflow integration.

### 4. Template Structure Alignment
All templates include:
- Context section
- Research section  
- Analysis section
- Recommendations section
- Integration section
- Validation section (with appropriate complexity)

**Rationale:** Predictable structure aids workflow integration and agent understanding.

## Differentiated Elements

Commands have different validation levels and documentation requirements based on their purpose:

### Brainstorm Command (Research-Focused)

**Purpose:** Fast, creative ideation with research validation
**Validation Level:** Lightweight (6-item checklist)
**Documentation:** Optional process logging

**Design Rationale:**
- **Speed Priority:** Brainstorming should be fast and creative
- **Flexibility:** Research exploration benefits from adaptive approaches
- **Creative Focus:** Heavy documentation requirements can stifle ideation
- **Research Nature:** Exploratory research doesn't need rigid process tracking

**Validation Approach:**
- Research source validation
- Solution category exploration
- Evidence-based feasibility assessment
- Clear recommendations for next steps

### Feature Proposal Command (Requirements-Focused)

**Purpose:** Precise requirements definition with comprehensive analysis
**Validation Level:** Comprehensive (4-section, 25+ item checklist)
**Documentation:** Mandatory process tracking

**Design Rationale:**
- **Precision Priority:** Requirements need thorough analysis and validation
- **Accountability:** Complex deliverables require process traceability
- **Quality Assurance:** Detailed validation catches critical gaps (proven in testing)
- **Handoff Preparation:** PRD development needs comprehensive structured input

**Validation Approach:**
- Module access documentation
- Tool usage contribution tracking
- Content quality verification
- Template compliance validation

## Command-Specific Justifications

### Why Different Validation Levels?

**Research vs. Requirements:**
- **Brainstorm:** Exploration and creativity benefit from lighter process overhead
- **Feature Proposal:** Precision and completeness require rigorous validation

**Deliverable Complexity:**
- **Brainstorm:** Ideas and approaches (moderate complexity)
- **Feature Proposal:** Detailed requirements for PRD development (high complexity)

**Downstream Impact:**
- **Brainstorm:** Informs proposal development (contained impact)
- **Feature Proposal:** Drives entire project planning and execution (broad impact)

### Why Consistent Language Patterns?

**Agent Learning:**
- Consistent instruction formats reduce cognitive load
- Predictable patterns improve execution reliability
- Clear purpose specification eliminates ambiguity

**Maintenance Benefits:**
- Updates can follow established patterns
- New commands can adopt proven structures
- Documentation remains coherent across commands

## Future Command Development

When creating new commands, follow this decision framework:

### Validation Level Decision Tree

**High Validation (Feature-Proposal Style):**
- Complex deliverables requiring precision
- Significant downstream impact
- Multiple stakeholder dependencies
- Critical quality requirements

**Medium Validation (Custom Level):**
- Moderate complexity deliverables
- Some downstream impact
- Internal team dependencies
- Standard quality requirements

**Light Validation (Brainstorm Style):**
- Exploratory or creative deliverables
- Limited downstream impact
- Individual contributor focus
- Speed and flexibility priorities

### Consistency Requirements

**Must Be Consistent:**
- Module reference patterns
- Tool usage instruction language
- Integration section format
- Basic template structure

**Can Be Different:**
- Validation complexity and depth
- Documentation requirements
- Tool usage rigor
- Process tracking detail

## Quality Assurance

### Testing Validation
Our testing revealed that lightweight validation missed critical quality issues:
- Template compliance failures
- Missing acceptance criteria
- Incomplete risk assessments
- Poor workflow integration preparation

This validates the decision for comprehensive validation on complex deliverables.

### Agent Confusion Prevention
Standardized language patterns prevent:
- Uncertainty about module access requirements
- Inconsistent tool usage approaches
- Unclear handoff expectations
- Variable output quality

## Implementation Notes

### Backward Compatibility
These design principles maintain compatibility with:
- Existing workflow sequences
- Current template structures
- Established module references
- Proven integration patterns

### Forward Compatibility
This framework supports:
- Additional command types
- Extended workflow sequences
- Enhanced validation requirements
- Improved automation capabilities

## Summary

The command framework balances consistency with purpose-driven flexibility:

- **Standardized patterns** prevent agent confusion
- **Differentiated validation** matches complexity to requirements
- **Clear rationale** enables informed command development
- **Quality assurance** ensures reliable deliverable production

This approach provides reliable, predictable command execution while optimizing validation overhead for command-specific needs.