# Test-Driven Development (TDD) Guide

## Task

You are implementing a new feature or fixing a bug using the Test-Driven Development (TDD) methodology. Your primary directive is to write a failing test _before_ you write the corresponding implementation code. This process will guide the development from requirements to clean, working code.

## The TDD Philosophy: Red-Green-Refactor

The core of TDD is the **Red-Green-Refactor** cycle. This is the fundamental pattern you must follow.

- **🔴 Red**: Write a small, automated test for a new piece of functionality. This test **must fail** initially because the functionality doesn't exist yet. This proves that the test is working correctly.
- **🟢 Green**: Write the **absolute minimum** amount of implementation code necessary to make the test pass. Do not add extra logic or features not demanded by the test.
- **🔵 Refactor**: With the safety of a passing test, improve the implementation code's structure, readability, and performance without changing its external behavior.

## Pre-Development Checklist

Before writing any code (test or implementation):

1.  **Understand Requirements**

    - Clearly define the acceptance criteria for the smallest piece of functionality you will build first. Break the problem down into tiny, testable steps.

2.  **Identify First Scenario**

    - Choose one specific requirement to build (e.g., a single happy path or a specific error condition). Do not try to test everything at once.

3.  **Locate Test Files**
    - Identify the correct location for your new test file, following existing project conventions.

## The TDD Workflow

Execute the following cycle for each piece of new functionality.

### Step 1: Write a Failing Test (Red)

Create a new, single test case for the scenario you identified. Write an assertion that checks for the desired outcome of that scenario. Run the test and **watch it fail**. This is a critical step. If it doesn't fail, your test is wrong or the code already exists.

### Step 2: Write Code to Pass the Test (Green)

Write the simplest possible implementation code to make the failing test pass. Do not write more code than is necessary. If returning a hardcoded value makes the test pass, do that first. Run all tests and confirm they now all pass.

### Step 3: Refactor the Code (Refactor)

Now that you have a passing test as a safety net, look for ways to improve the implementation code. Remove duplication, improve variable names, and simplify logic. Re-run all tests after each small refactoring to ensure you haven't broken anything.

### Step 4: Repeat

Select the next requirement or scenario and repeat the Red-Green-Refactor cycle. Continue this process until the entire feature is complete.

## Common Pitfalls

AVOID these common TDD mistakes:

- ❌ Writing the implementation code before writing a failing test.
- ❌ Writing more than one failing test at a time. The cycle should be one test at a time.
- ❌ Writing more implementation code than is needed to pass the current test.
- ❌ Forgetting the "Refactor" step. This is essential for maintaining code quality.
- ❌ Writing tests that are too large and cover too many requirements at once. Keep tests small and focused.

## Completion Checklist

**CRITICAL:** Before marking the task as complete:

- [ ] Every line of new implementation code was written in response to a specific failing test.
- [ ] The final implementation code is clean and has been refactored.
- [ ] All tests are passing.
- [ ] The implemented code meets all the requirements from the original task.
