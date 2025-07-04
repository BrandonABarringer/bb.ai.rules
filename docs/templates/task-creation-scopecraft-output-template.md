# Task Creation Scopecraft Output Template

## Agent Instructions

When executing `/project:task-creation`, use this template to ensure high-quality Scopecraft tasks with complete, actionable content. This template focuses on task content quality, not documentation.

**CRITICAL:** Every section must have substantive content. No empty sections or placeholders allowed.

## Required Output Structure

### Extended Thinking Mode Documentation
**Module Access Log:** [Document each module accessed with Read tool]
- @docs/modules/thinking-mode.md: Task structuring decisions and complexity analysis
- @docs/modules/workflow-integration.md: Integration with previous workflow commands
- @docs/modules/tool-usage-patterns.md: Tool sequences for task content research
- @docs/modules/template-integration.md: Template compliance for task sections
- @docs/modules/output-structure.md: Content formatting requirements

**Task Structuring Decisions:**
- Complexity assessment: [Simple task vs parent/subtasks decision]
- Content generation approach: [How to ensure complete sections]
- Quality validation plan: [How to verify developer-readiness]

### Pre-Creation Quality Checklist
Before creating any Scopecraft task, verify:
- [ ] Instruction section drafted with 200+ words of context
- [ ] Tasks checklist contains 5+ specific, actionable items
- [ ] Deliverable section defines clear acceptance criteria
- [ ] No generic placeholders like "Break down into subtasks"
- [ ] Developer can start work without clarification needed

### Task Creation Process

#### 1. Project Context Verification
```
mcp__scopecraft__get_current_root
```
- Project root: [Verified path]
- Existing tasks checked: [Number of related tasks found]
- Duplication avoided: [How uniqueness ensured]

#### 2. Task Content Research
**Pattern Analysis:**
- Similar tasks analyzed: [List task IDs reviewed]
- Best practices identified: [Key patterns found]
- Content quality examples: [Good examples noted]

**Domain Research:**
- Technical requirements: [Specific technologies/approaches]
- Industry standards: [Relevant practices]
- Implementation patterns: [Common approaches]

#### 3. Task Hierarchy Decision
**Decision Criteria Applied:**
- Estimated effort: [Hours/days/weeks]
- Number of deliverables: [Count of distinct outputs]
- Dependencies: [Related tasks or prerequisites]
- **Decision:** [Simple task / Parent with subtasks]
- **Rationale:** [Why this structure chosen]

### Scopecraft Task Content Generation

#### For Simple Tasks

**INSTRUCTION SECTION (Minimum 200 words):**
```markdown
## Instruction
[Comprehensive context paragraph explaining the background and why this task exists]

[Technical requirements paragraph detailing specific technologies, approaches, and constraints]

[Success criteria paragraph defining what constitutes task completion]

**Key Objectives:**
- [Specific objective 1]
- [Specific objective 2]
- [Specific objective 3]

**Technical Context:**
- [Relevant system/component]
- [Integration points]
- [Performance requirements]

**Constraints:**
- [Time/resource limitations]
- [Technical constraints]
- [Business requirements]
```

**TASKS CHECKLIST (Minimum 5 specific items):**
```markdown
## Tasks
- [ ] [Specific action verb] [specific component/feature] with [specific requirement]
- [ ] Research [specific technology/approach] for [specific purpose]
- [ ] Implement [specific functionality] including [specific features]
- [ ] Create unit tests for [specific components] covering [specific scenarios]
- [ ] Update documentation for [specific changes] in [specific location]
- [ ] Configure [specific system] to support [specific requirement]
- [ ] Validate [specific functionality] meets [specific criteria]
- [ ] Review code with focus on [specific concerns]
```

**DELIVERABLE SECTION (Clear acceptance criteria):**
```markdown
## Deliverable
[Primary deliverable description with specific requirements]

**Acceptance Criteria:**
- Functionality: [Specific working features]
- Performance: [Specific metrics to meet]
- Quality: [Specific standards to maintain]
- Documentation: [Specific docs to create/update]

**Definition of Done:**
- [ ] Code implemented and reviewed
- [ ] Tests written and passing (coverage target)
- [ ] Documentation updated
- [ ] Performance benchmarks met
- [ ] Security review completed
```

#### For Parent Tasks

**OVERVIEW INSTRUCTION (Minimum 300 words):**
```markdown
## Instruction
[Comprehensive overview of the entire feature/initiative]

[Business context and strategic importance]

[Technical architecture and approach]

[Success metrics and timeline]

**Subtask Breakdown:**
1. [Subtask 1 title]: [Brief description and importance]
2. [Subtask 2 title]: [Brief description and importance]
3. [Subtask 3 title]: [Brief description and importance]

**Dependencies and Risks:**
- [Key dependencies between subtasks]
- [Technical risks and mitigation]
- [Resource requirements]
```

### Quality Validation Checkpoints

#### Pre-Creation Validation
**Instruction Section Check:**
- [ ] Provides complete context (background, objectives, constraints)
- [ ] Includes technical requirements and approach
- [ ] Defines clear success criteria
- [ ] Contains 200+ words of substantive content
- [ ] **FAIL if:** Generic, vague, or under 100 words

**Tasks Checklist Check:**
- [ ] Each item is specific and actionable
- [ ] No generic items like "implement feature" without specifics
- [ ] Includes research, implementation, testing, and documentation tasks
- [ ] Contains 5+ concrete tasks
- [ ] **FAIL if:** Generic placeholders or fewer than 3 specific tasks

**Deliverable Section Check:**
- [ ] Clearly defines expected outcomes
- [ ] Includes measurable acceptance criteria
- [ ] Specifies quality standards
- [ ] Provides definition of done
- [ ] **FAIL if:** Vague outcomes or missing acceptance criteria

#### Post-Creation Validation
After task creation, verify using:
```
mcp__scopecraft__task_get --id [task-id]
```
- [ ] All sections have content (no empty strings)
- [ ] Content matches quality standards
- [ ] Task is immediately executable
- [ ] No updates needed before developer can start

### Anti-Patterns to Avoid

**❌ BAD - Empty Instruction:**
```markdown
## Instruction
Implement the feature as discussed.
```

**❌ BAD - Generic Tasks:**
```markdown
## Tasks
- [ ] Break down into subtasks
- [ ] Implement the feature
- [ ] Test it
```

**❌ BAD - Vague Deliverable:**
```markdown
## Deliverable
Working implementation
```

**✅ GOOD - Complete Instruction:**
```markdown
## Instruction
Implement a real-time notification system for the application that supports both in-app and email notifications. The system should handle user preferences, delivery scheduling, and retry logic for failed notifications.

The notification service will integrate with our existing event system and must support high-volume scenarios (10k+ notifications per minute). We'll use Redis for queuing and PostgreSQL for persistence.

**Key Requirements:**
- Support multiple notification channels (in-app, email, future: SMS)
- User preference management with opt-in/opt-out per notification type
- Delivery scheduling with timezone support
- Retry logic with exponential backoff
- Analytics tracking for delivery rates
```

### Final Quality Checklist

Before completing the task-creation command:
- [ ] Every created task has complete Instruction (200+ words)
- [ ] Every created task has actionable Tasks checklist (5+ items)
- [ ] Every created task has clear Deliverable with criteria
- [ ] No empty sections or placeholders exist
- [ ] Tasks are organized in logical workflow order
- [ ] Parent/subtask relationships are clear
- [ ] All tasks are immediately executable by developers

## Command Completion

**Success Criteria:**
- All tasks created with complete content
- Quality validation passed for each task
- No empty sections or generic content
- Developer can begin work immediately

**Report Format:**
```
Successfully created [N] high-quality Scopecraft tasks:
- [Task ID]: [Task Title] - [Simple/Parent/Subtask]
  - Instruction: [Word count] words
  - Tasks: [Number] actionable items  
  - Deliverable: Clear criteria defined
  
All tasks validated for completeness and developer-readiness.
```

## Template Usage Notes

- This template ensures task CONTENT quality, not just structure
- Every task must be immediately actionable by developers
- Generic or placeholder content is a validation failure
- Focus on creating fewer, higher-quality tasks rather than many shells
- When in doubt, add more specific content rather than less