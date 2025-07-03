# Template Integration Module

## Template Usage Requirements

### Template Access Pattern
All commands must reference and use designated templates:

```markdown
1. Use `Read` tool to access template structure from `@docs/templates/[template-name].md`
2. Follow template format exactly
3. Replace all bracketed placeholders with actual content
4. Complete validation checklist before finishing
5. Ensure all template sections are populated
```

### Template Reference Instructions
**In Command Structured Presentation Section:**
```markdown
Use `Read` tool to access the template structure from `@docs/templates/[command-name]-output-template.md` and follow its format exactly:
```

### Available Templates
- `@docs/templates/brainstorm-output-template.md`
- `@docs/templates/feature-proposal-output-template.md`
- `@docs/templates/[future-command]-output-template.md`

## Template Compliance Validation

### Required Validation Steps
1. **Structure Check:** Verify all template sections are included
2. **Content Check:** Ensure all placeholders are replaced with actual content
3. **Format Check:** Maintain consistent markdown formatting
4. **Checklist Check:** Complete template-specific validation checklist
5. **Integration Check:** Ensure Integration section prepares for next command

### Template Validation Checklist
Before completing any command output, verify:
- [ ] Template structure followed exactly
- [ ] All bracketed placeholders replaced
- [ ] Required sections completed
- [ ] Template-specific checklist completed
- [ ] Integration section prepared for next command
- [ ] File saved with correct naming convention

## Cross-Template Integration

### Template Chaining
Templates are designed to work together in workflow sequence:
- Brainstorm template Integration section prepares for Feature Proposal
- Feature Proposal template Integration section prepares for Feature PRD
- Each template builds on previous command outputs

### Template Data Flow
```markdown
Template N Output → Template N+1 Input
- Integration section provides required inputs
- Structured data enables seamless command chaining
- Validation ensures completeness for next step
```

## Template Customization Guidelines

### When to Customize Templates
- Adding new command types to workflow
- Extending existing command capabilities
- Supporting additional output formats
- Integrating with external systems

### Customization Best Practices
- Maintain core structure integrity
- Preserve Integration section format
- Include validation checklists
- Document customizations clearly
- Test integration with existing commands

## Usage in Commands

Reference this module in command instructions with:
```markdown
See @docs/modules/template-integration.md for template usage requirements.
```

## Integration with Other Modules

### Module Dependencies
- **Output Structure:** Templates must follow standardized directory structure
- **Tool Usage:** Templates accessed via `Read` tool, outputs via `Write` tool
- **Thinking Mode:** Complex templates benefit from visible reasoning process

### Module Coordination
```markdown
1. Enable thinking mode (@docs/modules/thinking-mode.md)
2. Use standard tools (@docs/modules/tool-usage-patterns.md)
3. Access templates (@docs/modules/template-integration.md)
4. Create structured outputs (@docs/modules/output-structure.md)
5. Enable workflow integration (@docs/modules/workflow-integration.md)
```

## Error Prevention

### Common Template Issues
1. **Missing sections:** Use template as checklist
2. **Incorrect formatting:** Follow template structure exactly
3. **Incomplete integration:** Ensure next command has required inputs
4. **Placeholder remnants:** Replace all bracketed content

### Validation Strategies
1. **Pre-completion check:** Review template compliance
2. **Integration verification:** Confirm next command readiness
3. **Format consistency:** Maintain markdown standards
4. **Content completeness:** Ensure substantive content in all sections