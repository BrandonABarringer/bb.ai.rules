---
category: "coding"
applies_to: ["claude", "gpt", "generic"]
framework: "react"
---

# React Framework Standards

## Component Architecture
Follow modern React component patterns and best practices.

### Context
- Functional components
- Component organization
- State management

### Behavior
- Use functional components with hooks instead of class components
- Implement proper component composition over inheritance
- Keep components small and focused on single responsibility
- Use TypeScript for all React components and props
- Define proper prop types and interfaces
- Create dedicated component folders containing all related files
- Include component-specific styles (CSS or Tailwind) within component folders
- Add README.md files to component folders documenting props and usage
- Design components to be self-contained and data-driven
- Make components container-agnostic but responsive to container size
- Plan component layouts to adapt based on available container space
- When using Tailwind, organize utility classes logically within components
- Use meaningful component and prop names

## Hooks and State Management
Use React hooks effectively and manage state properly.

### Context
- Component state
- Side effects
- Performance optimization

### Behavior
- Use useState for local component state
- Use useEffect for side effects with proper cleanup
- Implement custom hooks for reusable logic
- Use useCallback and useMemo for performance optimization when needed
- Avoid unnecessary re-renders with proper dependency arrays
- Use useContext for shared state when appropriate
- Implement proper error boundaries for error handling

## Accessibility (a11y)
Ensure React components are accessible to all users.

### Context
- Screen reader compatibility
- Keyboard navigation
- WCAG compliance

### Behavior
- Use semantic HTML elements and proper ARIA attributes
- Implement proper focus management and keyboard navigation
- Use accessible form labels and error messages
- Provide alternative text for images and icons
- Ensure sufficient color contrast ratios
- Test components with screen readers and keyboard-only navigation
- Use React accessibility testing tools and linters
- Implement proper heading hierarchy and landmark roles
- Handle dynamic content updates for assistive technologies
- Provide skip links and focus indicators where needed

## Performance Optimization
Write performant React components.

### Context
- Component rendering
- Bundle size
- User experience

### Behavior
- Use React.memo for expensive components when appropriate
- Implement code splitting with React.lazy and Suspense
- Optimize bundle size with proper imports
- Use key props correctly in lists
- Avoid inline object and function creation in render
- Profile components with React DevTools when performance issues arise
- Use proper loading states and error handling

## Security and Best Practices
Follow React security guidelines and modern patterns.

### Context
- User input handling
- XSS prevention
- Data flow

### Behavior
- Sanitize user input and avoid dangerouslySetInnerHTML when possible
- Use proper form validation and controlled components
- Implement proper error boundaries and fallback UI
- Follow unidirectional data flow principles
- Use proper event handling patterns
- Avoid direct DOM manipulation when possible
- Use React's built-in security features and avoid bypassing them