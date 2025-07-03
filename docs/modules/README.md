# Modular Documentation Components

## Overview

This directory contains reusable documentation modules that can be referenced across multiple slash commands, templates, and documentation files. This modular approach eliminates duplication, ensures consistency, and simplifies maintenance.

## Available Modules

### Core Behavior Modules
- **thinking-mode.md** - Extended thinking mode requirements for complex analysis
- **tool-usage-patterns.md** - Standard patterns for Claude Code tool usage
- **output-structure.md** - Standardized output organization and file management
- **template-integration.md** - Template usage and validation requirements
- **workflow-integration.md** - Command chaining and data flow management

## Module Usage Pattern

### In Slash Commands
Reference modules using the `@docs/modules/` syntax:
```markdown
### Section Name
See @docs/modules/[module-name].md for [specific requirements].

[Additional command-specific instructions]
```

### In Templates
Add module references in the Agent Instructions section:
```markdown
**Module References:**
- Extended thinking: @docs/modules/thinking-mode.md
- Tool usage: @docs/modules/tool-usage-patterns.md
- [Additional relevant modules]
```

### In Documentation
Reference modules for shared concepts:
```markdown
For detailed information on [topic], see @docs/modules/[module-name].md
```

## Benefits of Modular Approach

### Consistency
- **Standardized Behavior:** All commands use the same patterns for common tasks
- **Unified Language:** Consistent terminology and instructions across documentation
- **Reduced Errors:** Single source of truth prevents conflicting instructions

### Maintainability
- **Single Updates:** Changes to common patterns only need to be made once
- **Version Control:** Module changes are tracked and can be reviewed systematically
- **Impact Analysis:** Easy to see which commands are affected by module changes

### Scalability
- **Easy Extension:** New commands can quickly adopt proven patterns
- **Reusable Components:** Common functionality doesn't need to be recreated
- **Flexible Architecture:** Modules can be combined as needed for complex workflows

## Module Development Guidelines

### Creating New Modules
1. **Identify Common Patterns:** Look for repeated instructions across multiple commands
2. **Abstract Core Concepts:** Extract the essential, reusable elements
3. **Design for Reuse:** Make modules general enough for multiple use cases
4. **Document Integration:** Explain how modules work with other components

### Module Structure
```markdown
# Module Name

## Instructions for Agent Execution
[Core instructions that can be referenced]

## Usage in Commands
[How to reference this module in slash commands]

## Integration Notes
[How this module works with other modules]

## Best Practices
[Guidelines for effective usage]
```

### Module Maintenance
- **Regular Review:** Ensure modules stay current with command evolution
- **Impact Testing:** Test module changes across all referencing commands
- **Documentation Sync:** Keep module usage examples up to date
- **Feedback Integration:** Incorporate learnings from command usage

## Integration Examples

### Basic Module Reference
```markdown
### Tool Usage
See @docs/modules/tool-usage-patterns.md for standard tool usage requirements.
```

### Multiple Module Reference
```markdown
### Structured Output
See @docs/modules/template-integration.md for template usage requirements.
See @docs/modules/output-structure.md for output organization requirements.
```

### Module Combination
```markdown
### Workflow Integration
See @docs/modules/workflow-integration.md for command chaining requirements.

This is the [position] command in the workflow sequence. Ensure Integration section prepares for `/project:[next-command]` command.
```

## Module Dependencies

### Core Dependencies
- **thinking-mode.md** - Used by commands requiring complex analysis
- **tool-usage-patterns.md** - Used by all commands that interact with tools
- **output-structure.md** - Used by all commands that create outputs

### Workflow Dependencies
- **template-integration.md** - Depends on output-structure.md
- **workflow-integration.md** - Depends on output-structure.md and template-integration.md

### Integration Chain
```
thinking-mode.md
tool-usage-patterns.md
output-structure.md
├── template-integration.md
└── workflow-integration.md
```

## Best Practices for Module Usage

### Command Design
- **Reference Early:** Include module references at the beginning of relevant sections
- **Stay Focused:** Let modules handle common patterns, keep commands focused on specific logic
- **Avoid Duplication:** Don't repeat module content in commands
- **Maintain Context:** Provide command-specific context that modules can't

### Template Design
- **Include References:** List relevant modules in template instructions
- **Leverage Modules:** Use module patterns for template structure and validation
- **Document Integration:** Explain how modules apply to template usage
- **Maintain Specificity:** Keep template-specific requirements separate from module content

### Documentation Writing
- **Module First:** Check if content belongs in a module before adding to specific docs
- **Reference Consistently:** Use standard syntax for module references
- **Update Together:** When updating modules, review all referencing documents
- **Test Integration:** Verify that module references work correctly in context

## Future Expansion

### Planned Modules
- **validation-patterns.md** - Common validation and error-checking patterns
- **integration-testing.md** - Testing patterns for command integration
- **documentation-standards.md** - Standards for creating new documentation

### Module Evolution
- Modules will evolve based on usage patterns and feedback
- New common patterns will be extracted into modules
- Modules may be split or combined as architecture matures
- Integration patterns will be refined based on real-world usage