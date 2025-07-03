# Git Flow Strategy for Command Framework Testing

## Overview
Use feature branches for each testing task to ensure safe, isolated testing with easy rollback and merge capabilities.

## Branch Naming Convention
```
testing/task-[NN]-[short-description]
```

Examples:
- `testing/task-01-enhanced-brainstorm`
- `testing/task-02-brainstorm-validation`
- `testing/task-03-enhanced-feature-proposal`
- `testing/task-04-feature-proposal-validation`
- `testing/task-05-gap-analysis`
- `testing/task-06-implement-improvements`
- `testing/task-07-final-validation`

## Workflow Pattern

### For Each Task:
1. **Create Feature Branch**
   ```bash
   git checkout main
   git pull origin main  # if working with remote
   git checkout -b testing/task-[NN]-[description]
   ```

2. **Execute Task Work**
   - Run commands and generate outputs
   - Document findings and validation results
   - Make any necessary improvements

3. **Commit Progress**
   ```bash
   git add .
   git commit -m "Task [NN]: [description of work completed]"
   ```

4. **Complete Task**
   ```bash
   git add .
   git commit -m "Complete Task [NN]: [summary of results]"
   ```

5. **Decision Point:**
   - **If task successful:** Merge to main and continue
   - **If task reveals issues:** Keep branch for analysis, create fix branch

### Success Path (Normal Flow)
```bash
# Switch back to main
git checkout main

# Merge feature branch (fast-forward if possible)
git merge testing/task-[NN]-[description]

# Clean up feature branch
git branch -d testing/task-[NN]-[description]

# Create next task branch
git checkout -b testing/task-[NN+1]-[next-description]
```

### Issue Discovery Path
```bash
# Keep current branch for analysis
git checkout main

# Create fix branch
git checkout -b fix/task-[NN]-issues

# Implement fixes
# ... make changes ...
git add .
git commit -m "Fix issues found in task [NN]"

# Merge fix back to main
git checkout main
git merge fix/task-[NN]-issues

# Retry original task or proceed based on analysis
```

## Safety Features

### Rollback Options
```bash
# Rollback to main if task branch has issues
git checkout main
git branch -D testing/task-[NN]-[description]  # Delete problematic branch

# Rollback main to before testing started
git reset --hard f22c872  # Our checkpoint commit

# Rollback to before specific task
git reset --hard [commit-before-task]
```

### Branch Status Checking
```bash
# See all branches
git branch -a

# See current branch status
git status

# See commit history
git log --oneline --graph --all

# Compare branches
git diff main testing/task-[NN]-[description]
```

## Integration Points

### Scopecraft MCP Integration
- Update task status in Scopecraft when creating branches
- Log git commands and branch names in task logs
- Document branch outcomes in task deliverables

### Validation Integration
- Commit validation results to task branches
- Include git branch info in validation reports
- Use branch history to track testing progression

## Emergency Procedures

### If Testing Breaks Everything
1. **Stop immediately**
2. **Document current state**
3. **Return to main:** `git checkout main`
4. **Full rollback:** `git reset --hard f22c872`
5. **Assess what went wrong**
6. **Plan recovery approach**

### If Partial Issues Found
1. **Complete current task on branch**
2. **Document issues in task deliverable**
3. **Switch to main:** `git checkout main`
4. **Create fix branch:** `git checkout -b fix/[issue-description]`
5. **Implement targeted fixes**
6. **Test fixes before merging**

## Best Practices

### Commit Messages
Use clear, descriptive commit messages:
```
Task 01: Execute enhanced brainstorm command for AI code review
Task 01: Document standardization patterns validation results
Task 01: Complete brainstorm baseline testing - PASSED
```

### Branch Lifecycle
- **Create:** At start of each task
- **Work:** All task execution on feature branch
- **Document:** All findings committed to branch
- **Decide:** Merge if successful, analyze if issues
- **Clean:** Delete feature branch after successful merge

### Documentation in Commits
- Include validation scores in commit messages
- Reference specific files modified or created
- Note any issues or concerns discovered
- Link to task deliverables and reports

## Recovery Scenarios

### Scenario 1: Task Fails Validation
```bash
# Stay on task branch, document failure
git add .
git commit -m "Task [NN]: FAILED validation - [specific issues]"

# Switch to main for analysis
git checkout main

# Keep failed branch for reference
# Create improvement branch
git checkout -b fix/task-[NN]-validation-issues
```

### Scenario 2: Command Framework Breaks
```bash
# Emergency rollback
git checkout main
git reset --hard f22c872

# Create recovery branch
git checkout -b recovery/command-framework-repair

# Implement conservative fixes
# ... work ...
git commit -m "Conservative fix for framework issues"
```

### Scenario 3: Conflicting Changes
```bash
# Use git merging to resolve conflicts
git checkout main
git merge testing/task-[NN]-[description]
# Resolve conflicts manually
git add .
git commit -m "Merge task [NN] with conflict resolution"
```

## Success Criteria

### Per Task
- ✅ Clean branch creation and management
- ✅ All work committed with clear messages
- ✅ Task deliverables include git information
- ✅ Successful merge or documented issue analysis

### Overall Testing
- ✅ Main branch remains stable throughout testing
- ✅ All successful improvements merged to main
- ✅ Issue branches preserved for analysis
- ✅ Clear git history showing testing progression
- ✅ Easy rollback capability maintained