# Scopecraft Task Quality Validation Checklist

**Purpose:** Evaluate the quality of actual Scopecraft tasks created by the task-creation command, focusing on content completeness and developer-readiness.

**Validation Target:** Scopecraft task files (.task.md and _overview.md files)  
**Pass Threshold:** 85/100 points  
**Focus:** Task content quality, not documentation or formatting

## Scoring System Overview

| Category | Points | Focus Area |
|----------|--------|------------|
| Instruction Quality | 25 | Context, requirements, objectives |
| Tasks Checklist Quality | 35 | Actionability, specificity, completeness |
| Deliverable Quality | 25 | Clarity, measurability, acceptance criteria |
| Overall Executability | 15 | Developer-readiness, no blockers |
| **Total** | **100** | **Complete, actionable tasks** |

## Detailed Scoring Criteria

### 1. Instruction Quality (25 points)

**Purpose:** Ensure developers have complete context to execute the task

#### Content Completeness (10 points)
- **10 points:** 200+ words with comprehensive context, background, objectives, and constraints
- **7 points:** 150-199 words with good context but missing some details
- **4 points:** 100-149 words with basic context
- **0 points:** Under 100 words or missing critical context

#### Technical Clarity (8 points)
- **8 points:** Clear technical approach, specific technologies mentioned, architecture decisions explained
- **5 points:** General technical direction provided but lacks specifics
- **2 points:** Vague technical guidance
- **0 points:** No technical direction provided

#### Success Criteria (7 points)
- **7 points:** Clear, measurable success criteria defined
- **4 points:** Success criteria present but somewhat vague
- **1 point:** Minimal success criteria
- **0 points:** No success criteria defined

**Automatic Failures (0 points for section):**
- Empty Instruction section
- Generic text like "Implement as discussed"
- Less than 50 words total

### 2. Tasks Checklist Quality (35 points)

**Purpose:** Ensure developers have specific, actionable steps to follow

#### Actionability (15 points)
- **15 points:** All tasks start with specific action verbs and define clear outcomes
- **10 points:** Most tasks are actionable with minor vagueness
- **5 points:** Mix of actionable and vague tasks
- **0 points:** Mostly vague or non-actionable items

#### Specificity (10 points)
- **10 points:** Each task mentions specific components, files, or features
- **7 points:** Most tasks are specific with some general items
- **3 points:** Half specific, half generic
- **0 points:** Mostly generic tasks without specifics

#### Completeness (10 points)
- **10 points:** 7+ well-structured tasks covering research, implementation, testing, and documentation
- **7 points:** 5-6 good tasks covering main aspects
- **4 points:** 3-4 tasks with gaps in coverage
- **0 points:** Less than 3 tasks or major gaps

**Automatic Failures (0 points for section):**
- Contains "Break down into subtasks" or similar placeholders
- Less than 3 actionable items
- All items are generic without specifics

### 3. Deliverable Quality (25 points)

**Purpose:** Ensure clear definition of task completion

#### Outcome Clarity (10 points)
- **10 points:** Specific deliverables described with technical details
- **7 points:** Clear deliverables but lacking some specifics
- **3 points:** Vague deliverable description
- **0 points:** No clear deliverable defined

#### Acceptance Criteria (10 points)
- **10 points:** Measurable criteria with specific requirements (performance, quality, features)
- **7 points:** Good criteria but some are subjective
- **3 points:** Basic criteria provided
- **0 points:** No acceptance criteria

#### Definition of Done (5 points)
- **5 points:** Clear checklist for task completion including code, tests, docs
- **3 points:** Basic completion definition
- **0 points:** No definition of done

**Automatic Failures (0 points for section):**
- Empty Deliverable section
- Single line like "Working implementation"
- No measurable criteria

### 4. Overall Executability (15 points)

**Purpose:** Ensure developer can start immediately without clarification

#### Immediate Actionability (8 points)
- **8 points:** Developer can start work immediately with no questions
- **5 points:** Minor clarifications might be needed
- **2 points:** Several clarifications needed
- **0 points:** Major blockers or unclear requirements

#### Dependencies and Context (7 points)
- **7 points:** All dependencies identified, context clear, integration points defined
- **4 points:** Most dependencies clear with minor gaps
- **1 point:** Significant dependency or context gaps
- **0 points:** Critical dependencies missing

## Validation Process

### Step 1: Task Retrieval
```bash
mcp__scopecraft__task_get --id [task-id]
```

### Step 2: Section Analysis
For each task, evaluate:
1. **Instruction section:** Word count, context quality, technical clarity
2. **Tasks section:** Count items, check specificity, verify actionability
3. **Deliverable section:** Check criteria, measurability, completeness

### Step 3: Scoring
Apply scoring rubric to each section and calculate total.

## Examples

### High-Quality Task (95/100)

**Instruction (24/25):**
```markdown
Implement a distributed caching layer using Redis to improve API response times for frequently accessed user data. The current database queries for user profiles average 150ms, causing poor user experience during peak hours.

The caching layer should integrate with our existing Node.js API services and support cache invalidation on user updates. We'll use Redis Cluster for high availability with a 3-node setup in production.

**Technical Requirements:**
- Redis 7.0+ with cluster mode
- Node.js Redis client with cluster support
- Cache TTL of 1 hour for user data
- Automatic cache warming for active users
- Monitoring via Prometheus metrics

**Success Criteria:**
- API response time reduced to <20ms for cached data
- 95%+ cache hit rate for active users
- Zero data inconsistency issues
- Graceful fallback when cache unavailable
```

**Tasks (33/35):**
```markdown
- [ ] Research Redis Cluster setup best practices for our AWS environment
- [ ] Implement Redis connection manager with cluster support in lib/cache/
- [ ] Create caching middleware for Express routes in middleware/cache.js
- [ ] Add cache invalidation logic to user update endpoints in controllers/user.js
- [ ] Implement cache warming job for active users using Bull queue
- [ ] Add Prometheus metrics for cache hit/miss rates and latency
- [ ] Create integration tests for cache scenarios in test/cache/
- [ ] Update API documentation with caching behavior details
- [ ] Configure Redis Cluster in staging environment
- [ ] Load test caching layer with expected production traffic
```

**Deliverable (23/25):**
```markdown
Production-ready caching layer that reduces API response times for user data endpoints.

**Acceptance Criteria:**
- Response time: <20ms for cached requests (from 150ms)
- Cache hit rate: >95% for active users
- Availability: Handles Redis node failures gracefully
- Monitoring: Full metrics dashboard in Grafana
- Documentation: Architecture diagram and runbook

**Definition of Done:**
- [ ] Code reviewed and approved
- [ ] Unit tests pass with 90%+ coverage
- [ ] Integration tests verify cache behavior
- [ ] Load tests confirm performance targets
- [ ] Staging deployment successful
- [ ] Documentation complete
```

### Low-Quality Task (25/100)

**Instruction (5/25):**
```markdown
Add caching to improve performance as discussed in the meeting.
```

**Tasks (10/35):**
```markdown
- [ ] Set up caching
- [ ] Implement cache logic
- [ ] Test it
- [ ] Deploy
```

**Deliverable (5/25):**
```markdown
Working cache implementation that improves performance.
```

## Penalty Conditions

**Automatic Score Reductions:**
- -10 points: Any empty section (Instruction, Tasks, or Deliverable)
- -15 points: Generic placeholders found (e.g., "Break down into subtasks")
- -20 points: Task cannot be executed without significant clarification
- -5 points: No technical specifics in any section

## Reporting Format

```markdown
# Scopecraft Task Quality Validation Report

**Task ID:** [task-id]
**Task Title:** [title]
**Validation Date:** [date]

## Scoring Summary

| Section | Score | Max | Percentage |
|---------|-------|-----|------------|
| Instruction Quality | X | 25 | X% |
| Tasks Checklist | X | 35 | X% |
| Deliverable Quality | X | 25 | X% |
| Overall Executability | X | 15 | X% |
| **Total** | **X** | **100** | **X%** |

**Pass/Fail:** [PASS/FAIL] (85+ required)

## Detailed Findings

### Strengths
- [Specific examples of good content]

### Weaknesses
- [Specific content quality issues]

### Recommendations
- [Specific improvements needed]
```

## Quick Reference Card

### Minimum Requirements for PASS (85+)
- **Instruction:** 150+ words with clear context and objectives
- **Tasks:** 5+ specific, actionable items (no placeholders)
- **Deliverable:** Clear outcome with measurable criteria
- **Overall:** Developer can start work immediately

### Common Failures
- ❌ Empty sections or "TBD" content
- ❌ Generic tasks without specifics
- ❌ Vague deliverables without criteria
- ❌ Missing technical context
- ❌ Placeholder content like "Break down into subtasks"