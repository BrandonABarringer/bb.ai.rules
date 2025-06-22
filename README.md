# AI Agent Rules Mono Repo

Centralized repository of reusable AI agent behavioral rules that can be selectively integrated into projects via git subtree.

## Structure

- `behavioral/` - Core behavioral guidelines (communication, task execution, security, error handling)
- `coding/languages/` - Language-specific standards (PHP, TypeScript, CSS, HTML)
- `coding/frameworks/` - Framework guidelines (WordPress, Elementor, React, Tailwind)
- `contextual/` - Role-specific rules (frontend, backend, full-stack, code reviewer)
- `templates/` - Templates for creating new rules and project integration

## Multi-Agent Compatibility

Works with Claude Code, Cursor, Windsurf, and other AI development tools. Use the cross-platform template for universal compatibility.

## Usage

### Recommended: Pull Everything (Simple & Complete)

```bash
# Add all AI agent rules to your project
git subtree add --prefix=ai-rules https://github.com/username/rwest.ai.rules.git main --squash
```

**Why include everything?**

- **Zero decision fatigue** - no need to choose specific categories
- **Future-proof** - rules available when project needs change
- **Minimal overhead** - entire rule set is ~150KB of text files
- **Consistent standards** - whole team uses same comprehensive ruleset
- **Cross-framework learning** - agents can reference best practices across technologies

### Alternative: Pull Specific Categories (Advanced)

If you prefer selective integration:

```bash
# Add specific categories only
git subtree add --prefix=ai-rules/behavioral https://github.com/username/rwest.ai.rules.git behavioral --squash
git subtree add --prefix=ai-rules/coding https://github.com/username/rwest.ai.rules.git coding --squash
git subtree add --prefix=ai-rules/contextual https://github.com/username/rwest.ai.rules.git contextual --squash
```

### Update Rules

```bash
# Update all rules (recommended approach)
git subtree pull --prefix=ai-rules https://github.com/BrandonABarringer/bb.ai.rules main --squash

# Update specific categories (if using selective approach)
git subtree pull --prefix=ai-rules/behavioral https://github.com/BrandonABarringer/bb.ai.rules behavioral --squash
```

### Project Integration

1. Copy `templates/cross-platform-rules.md` to your project
2. Configure for your AI tools:
   - **Claude Code**: Copy as `CLAUDE.md` in project root
   - **Cursor (Modern)**: Copy as `.cursor/rules/project-rules.mdc`
   - **Cursor (Legacy)**: Copy as `.cursorrules` in project root (deprecated)
   - **Windsurf**: Copy as `.windsurf/rules.md`
3. Pull relevant rule categories via git subtree

## Component Architecture Standards

All frameworks follow consistent component patterns:

- Components contained in dedicated folders with all related files
- README.md documentation for usage and props
- Container-agnostic design that responds to container size
- Self-contained and data-driven architecture

## Rule Format

All rules use Markdown with YAML frontmatter:

```markdown
---
category: "behavioral|coding|contextual"
applies_to: ["claude", "gpt", "generic"]
---

# Rule Category

## Specific Rule

Brief description

### Context

When this applies

### Behavior

What to do
```

Rules are kept simple and self-contained. Use git commit history to track changes and updates.
