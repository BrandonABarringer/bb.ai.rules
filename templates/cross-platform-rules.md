# AI Agent Rules for this Project

## Before Starting Work
Review the relevant AI agent rules in the `ai-rules/` directory:

- **Behavioral Rules**: `ai-rules/behavioral/` - Communication, task execution, security posture, error handling
- **Language Standards**: `ai-rules/coding/languages/` - PHP, TypeScript, CSS, HTML standards  
- **Framework Guidelines**: `ai-rules/coding/frameworks/` - WordPress, Elementor, React, Tailwind patterns
- **Role-Specific Rules**: `ai-rules/contextual/` - Frontend, backend, full-stack, code reviewer guidance

## Component Architecture Standards
All components across frameworks should:
- Be contained within their own folder with styles and functionality
- Be container-agnostic but responsive to container size
- Include README.md documentation for usage and props
- Be self-contained and data-driven

## Integration Notes
This file works with multiple AI development tools:

### **Claude Code**
- Copy this file as `CLAUDE.md` in project root (auto-loads)

### **Cursor (Modern - Recommended)**
- Create `.cursor/rules/` directory
- Copy this file as `.cursor/rules/project-rules.mdc`
- Enable Project Rules in Cursor settings

### **Cursor (Legacy - Deprecated)**
- Copy this file as `.cursorrules` in project root
- Will be removed in future Cursor versions

### **Windsurf**
- Copy this file to `.windsurf/rules.md`

### **Other AI Tools**
- Reference this file manually as needed

## Rule Updates
Rules are managed via git subtree from the central mono repo. Update with:
```bash
git subtree pull --prefix=ai-rules/[category] [repo-url] [branch] --squash
```