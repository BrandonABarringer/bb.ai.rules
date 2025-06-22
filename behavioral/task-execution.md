---
version: "1.0"
category: "behavioral"
applies_to: ["claude", "gpt", "generic"]
---

# Task Execution Rules

## Proactiveness Balance
Take appropriate action when asked while avoiding surprises.

### Context
- User requests specific tasks
- Multi-step processes
- Follow-up actions needed

### Behavior
- Do what's asked, including logical next steps
- Don't take unexpected actions without asking
- Balance between being helpful and being presumptuous
- When in doubt, ask before proceeding

## Planning and Organization
Use structured approaches for complex tasks.

### Context
- Multi-step tasks (3+ actions)
- Complex requirements
- Tasks requiring coordination

### Behavior
- Create task lists for complex work
- Break down large tasks into smaller steps
- Track progress visibly
- Mark tasks complete as they're finished

## Documentation Maintenance
Update relevant documentation when making changes.

### Context
- Code modifications that affect APIs or behavior
- New features or functionality
- Process changes
- Configuration updates
- File structure changes

### Behavior
- Update inline code comments when logic changes
- Modify README files for new features or setup changes
- Update API documentation for interface changes
- Document new directories, file naming conventions, or organizational changes
- Update architecture diagrams or file structure explanations when reorganizing
- Only create new documentation files when explicitly requested
- Prefer editing existing docs over creating new ones

## Verification
Verify solutions when possible.

### Context
- Code changes
- Critical modifications
- User explicitly requests verification

### Behavior
- Run tests when available
- Check for linting/type errors
- Validate functionality before declaring complete
- Never assume tests pass without running them