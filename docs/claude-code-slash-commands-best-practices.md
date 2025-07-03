# Claude Code Slash Commands: Best Practices & Structure

## Agent Instructions

When implementing Claude Code slash commands, follow these research-validated best practices for optimal performance and user experience.

## Command Structure & Syntax

### Basic Command Format
```
/<prefix>:<command-name> [arguments]
```

**Components:**
- `<prefix>`: Use `project` for team-shared commands, `user` for personal
- `<command-name>`: Lowercase, hyphen-separated (e.g., `code-review`, `create-feature`)
- `[arguments]`: Access via `$ARGUMENTS` keyword in command files

### Advanced Syntax Features
- **Namespacing**: `/project:category:command-name` using subdirectories
- **Bash Integration**: `!command` prefix executes bash before slash command
- **File References**: `@filepath` includes file contents in command context
- **Dynamic Parameters**: `$ARGUMENTS` passes user input to command

## File Organization Requirements

### Directory Structure
```
.claude/commands/
├── category1/
│   ├── command1.md
│   └── command2.md
├── category2/
│   └── command3.md
└── standalone.md
```

### File Naming Rules
- Use `.md` extension for all command files
- Lowercase with hyphens for multi-word commands
- Organize by logical workflow categories
- Filename becomes command name (e.g., `brainstorm.md` → `/project:brainstorm`)

## Required Command File Structure

### Mandatory Sections
```markdown
# Command Name

## Purpose
Single sentence describing command objective

## Usage
`/project:command-name [arguments]`

## Instructions
Step-by-step workflow for agent execution

## Expected Outcome
Specific deliverables and results

## Arguments
How to use $ARGUMENTS parameter

## Example Usage
Concrete usage examples
```

### Professional Command Components
1. **Clear Instructions**: Detailed agent workflow steps
2. **Tool Integration**: Specify which Claude Code tools to use
3. **Research Requirements**: External validation and analysis steps
4. **Thinking Mode**: Instructions to expose reasoning process
5. **Output Format**: Structured presentation requirements

## Agent Workflow Patterns

### Research-Driven Commands
When creating research-intensive commands:
- Use `WebSearch` for external validation
- Use `Grep/Glob` for codebase analysis
- Cross-reference findings across multiple sources
- Validate against existing implementations

### Thinking Mode Activation
Include these instructions for complex commands:
- "Enable extended thinking mode"
- "Expose your reasoning process"
- "Document exploration and decision-making"
- "Show multi-angle problem analysis"

### Tool Integration Sequences
Structure commands to use Claude Code tools systematically:
1. Research phase (WebSearch, Grep, Read)
2. Analysis phase (thinking mode, cross-validation)
3. Generation phase (structured output)
4. Integration phase (prepare for next workflow step)

## MCP Integration Guidelines

### Scopecraft MCP Commands
- Commands can trigger MCP task creation
- Use `mcp__scopecraft__*` functions for task management
- Integrate with existing project workflow systems
- Structure commands to prepare for task creation

### Dynamic Command Discovery
- MCP servers automatically expose prompts as slash commands
- Commands become available without manual registration
- Support complex workflow orchestration through MCP

## Command Implementation Best Practices

### Comprehensive Workflows
- Create end-to-end solutions, not isolated tasks
- Include validation and verification steps
- Design for automation with human oversight
- Ensure reproducibility across different projects

### Agent-Friendly Instructions
- Use imperative language for clear agent direction
- Specify exact tool usage patterns
- Include conditional logic for different scenarios
- Provide clear stopping points and success criteria

### Output Standardization
Structure command outputs consistently:
- **Context**: Problem understanding
- **Research**: Validation findings
- **Analysis**: Evidence-based conclusions
- **Recommendations**: Next steps
- **Integration**: Workflow preparation

## Team Collaboration Requirements

### Version Control
- Check `.claude/commands/` into git repository
- Include `CLAUDE.md` for shared team knowledge
- Document team-specific command conventions
- Maintain command changelog for updates

### Security Considerations
- Establish allowlist standards for command approval
- Review commands for sensitive information exposure
- Consider team permissions and access patterns
- Validate external research sources

## Integration with Existing Workflows

### Idea-to-Task Pipeline
Structure commands to support workflow progression:
1. `brainstorm` → research and ideation
2. `feature-proposal` → structured proposals
3. `feature-to-prd` → requirement documentation
4. `feature-planning` → implementation planning
5. `task-creation` → Scopecraft MCP task creation

### Command Chaining
- Design commands to prepare inputs for subsequent commands
- Include transition instructions between workflow steps
- Maintain context and state across command executions
- Enable workflow automation through command sequences

## Key Implementation Rules

1. **Agent-Centric Design**: Write instructions for AI execution, not human reading
2. **Tool Specification**: Explicitly state which Claude Code tools to use
3. **Research Integration**: Always validate through multiple sources
4. **Structured Output**: Use consistent formatting for predictable results
5. **Workflow Integration**: Design commands as part of larger processes
6. **Thinking Mode**: Include reasoning exposure for complex tasks
7. **Error Handling**: Provide fallback instructions for common issues

## Sources & References

Research validated through:
- Claude Code official documentation
- Professional command suites (Claude Command Suite)
- Community best practices (Awesome Claude Code)
- Industry implementation patterns