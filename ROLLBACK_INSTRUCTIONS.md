# Rollback Instructions

## Current Checkpoint
**Commit:** `f22c872` - Enhanced Command Framework Ready for Testing  
**Date:** 2025-07-03  
**Purpose:** Pre-testing checkpoint with all command framework enhancements

## Quick Rollback Commands

### Full Rollback to Previous State
```bash
# Reset to previous commit (before enhancements)
git reset --hard HEAD~1

# OR reset to specific commit if needed
git log --oneline  # to see commit history
git reset --hard <commit-hash>
```

### Partial Rollback Options

#### Rollback Just Command Files
```bash
git checkout HEAD~1 -- .claude/commands/
git commit -m "Rollback command files to previous state"
```

#### Rollback Just Templates
```bash
git checkout HEAD~1 -- docs/templates/
git commit -m "Rollback templates to previous state"
```

#### View Changes Made
```bash
git diff HEAD~1 HEAD  # See all changes in this checkpoint
git show f22c872      # See details of checkpoint commit
```

## Recovery Scenarios

### If Testing Reveals Critical Issues
1. **Stop testing immediately**
2. **Document issues found** in COMMAND_FRAMEWORK_STATUS.md
3. **Rollback using:** `git reset --hard HEAD~1`
4. **Restart with modified approach**

### If Partial Issues Found
1. **Complete current testing cycle**
2. **Use git to revert specific files** that have issues
3. **Continue with modified approach**

### If Framework Becomes Unstable
1. **Emergency rollback:** `git reset --hard f22c872^` (goes to commit before this one)
2. **Assess what worked vs. what didn't**
3. **Implement more conservative changes**

## File Location Reference

### Enhanced Files (Can be individually rolled back)
- `.claude/commands/01_brainstorm.md`
- `.claude/commands/02_feature-proposal.md`  
- `docs/templates/brainstorm-output-template.md`
- `docs/templates/feature-proposal-output-template.md`
- `docs/modules/tool-usage-patterns.md`

### New Files (Can be safely deleted)
- `docs/validation-checklists/feature-proposal-execution-checklist.md`
- `docs/command-design-principles.md`
- `COMMAND_FRAMEWORK_STATUS.md`
- `ROLLBACK_INSTRUCTIONS.md` (this file)

## Testing Safety
- All testing is read-only execution of existing commands
- No destructive operations planned
- Can safely test without risk to codebase
- Git provides complete safety net

## Contact Point
**Current Status:** Ready for safe testing with full rollback capability  
**Risk Level:** Very Low - comprehensive safety measures in place