# Cursor Modern Rules Setup

## Quick Setup for Cursor (2024+)

### 1. Create Directory Structure
```bash
mkdir -p .cursor/rules
```

### 2. Copy Rule Files
```bash
# Copy the cross-platform template as base rules
cp templates/cross-platform-rules.md .cursor/rules/project-rules.mdc

# Optional: Organize rules by category
cp templates/cross-platform-rules.md .cursor/rules/behavioral-rules.mdc
cp templates/cross-platform-rules.md .cursor/rules/coding-standards.mdc
```

### 3. Enable in Cursor Settings
- Open Cursor Settings
- Navigate to "Rules for AI" 
- Enable "Project Rules"
- Rules in `.cursor/rules/` will be auto-detected

## Rule Organization Options

### Single File Approach (Simple)
```
.cursor/
└── rules/
    └── project-rules.mdc (all rules in one file)
```

### Multi-File Approach (Organized)
```
.cursor/
└── rules/
    ├── behavioral-rules.mdc (communication, task execution)
    ├── coding-standards.mdc (language/framework specific)
    ├── component-architecture.mdc (component patterns)
    └── project-context.mdc (project-specific rules)
```

## Rule Priority in Cursor

Cursor evaluates rules in this priority order:
1. **Local (manual)**: Rules explicitly included with @ruleName
2. **Auto Attached**: Rules matching glob patterns
3. **User Rules**: Global rules from Cursor Settings

## Migration from Legacy .cursorrules

If you have an existing `.cursorrules` file:
1. Create `.cursor/rules/` directory
2. Copy content from `.cursorrules` to `.cursor/rules/project-rules.mdc`
3. Test that rules are working in Cursor
4. Remove `.cursorrules` file once confirmed

## Notes

- Use `.mdc` extension for rule files
- Rules are plain text/markdown format
- Currently works primarily in Agent mode
- Legacy `.cursorrules` still supported but deprecated