---
category: "coding"
applies_to: ["claude", "gpt", "generic"]
language: "typescript"
---

# TypeScript Coding Standards

## Type Safety
Leverage TypeScript's type system effectively.

### Context
- All TypeScript files
- Function definitions
- Variable declarations
- API interfaces

### Behavior
- Always use explicit types for function parameters and return values
- Define interfaces for object shapes
- Use union types instead of `any` when possible
- Prefer `unknown` over `any` for truly unknown types
- Use type guards for runtime type checking
- Enable strict mode in tsconfig.json
- Use const assertions for immutable data

## Code Style
Follow consistent formatting and naming conventions.

### Context
- Variable and function naming
- File organization
- Import statements

### Behavior
- Use camelCase for variables and functions
- Use PascalCase for classes, interfaces, and types
- Use UPPER_CASE for constants
- Use kebab-case for file names
- Group imports: external libraries, then internal modules
- Use explicit return types for exported functions
- Prefer const over let when values don't change

## Accessibility (a11y)
Ensure TypeScript applications support accessibility.

### Context
- Frontend applications
- User interface components
- Form handling
- Dynamic content

### Behavior
- Implement proper ARIA attributes and roles in DOM manipulation
- Ensure keyboard navigation works for all interactive elements
- Provide descriptive alt text and labels programmatically
- Support screen readers with semantic markup generation
- Test with assistive technologies and keyboard-only navigation
- Handle focus management properly in dynamic applications
- Use TypeScript to enforce accessibility props in components

## Security Practices
Implement secure TypeScript patterns.

### Context
- User input validation
- API calls
- Data serialization
- Environment variables

### Behavior
- Validate all external data with type guards or schema validation
- Never use `eval()` or `Function()` constructor
- Sanitize data before DOM manipulation
- Use environment variable validation at startup
- Implement proper error boundaries
- Avoid exposing sensitive data in client-side code
- Use Content Security Policy headers
- Validate and sanitize all user inputs

## Modern TypeScript Features
Use contemporary TypeScript syntax and features.

### Context
- TypeScript 4.0+ projects
- New code development
- Type definitions

### Behavior
- Use optional chaining (?.) and nullish coalescing (??)
- Implement template literal types when appropriate
- Use mapped types for transformations
- Leverage conditional types for complex type logic
- Use `as const` for readonly tuple types
- Implement generic constraints effectively
- Use utility types (Partial, Required, Pick, etc.)

## Performance Optimization
Write efficient TypeScript for optimal runtime performance.

### Context
- Bundle size optimization
- Runtime performance
- Memory management
- Loading strategies

### Behavior
- Use dynamic imports for code splitting
- Implement tree shaking with proper module exports
- Optimize bundle size with careful dependency management
- Use lazy loading for non-critical components
- Implement proper memoization for expensive calculations
- Monitor and profile TypeScript compilation performance
- Use efficient data structures and algorithms
- Minimize object creation in hot code paths