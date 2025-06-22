---
category: "coding"
applies_to: ["claude", "gpt", "generic"]
framework: "tailwind"
---

# Tailwind CSS Framework Standards

## Utility-First Approach
Use Tailwind's utility-first methodology effectively.

### Context
- Component styling
- Layout creation
- Responsive design

### Behavior
- Prefer utility classes over custom CSS when possible
- Use Tailwind's design system (spacing, colors, typography) consistently
- Combine utilities to create complex designs
- Use component extraction (@apply) sparingly for repeated patterns
- Leverage Tailwind's configuration for project-specific design tokens
- Use semantic class groupings for better readability
- Avoid fighting the framework with excessive custom CSS

## Class Organization
Organize Tailwind classes for readability and maintainability.

### Context
- Class ordering
- Code readability
- Team collaboration

### Behavior
- Group related utility classes together (layout, spacing, typography, colors)
- Use consistent ordering: layout → spacing → sizing → typography → colors → effects
- Use line breaks for complex class combinations when needed
- Use Tailwind's class sorting tools (Prettier plugin) when available
- Separate responsive utilities logically
- Use meaningful component names when extracting utilities

## Responsive Design
Implement responsive design using Tailwind's mobile-first approach.

### Context
- Mobile-first design
- Breakpoint management
- Cross-device compatibility

### Behavior
- Start with mobile styles, then add responsive prefixes (sm:, md:, lg:, xl:)
- Use Tailwind's default breakpoints unless project requires custom ones
- Test designs across all targeted breakpoints
- Use container queries (container:) when appropriate for component-based responsive design
- Avoid excessive breakpoint variations
- Use responsive utilities for spacing, typography, and layout adjustments

## Accessibility (a11y)
Ensure Tailwind implementations support accessibility.

### Context
- Color contrast
- Focus states
- Screen reader compatibility

### Behavior
- Use Tailwind's accessibility-focused utilities (sr-only, focus:, etc.)
- Maintain sufficient color contrast with Tailwind's color palette
- Implement proper focus states using focus: prefix utilities
- Use semantic HTML with Tailwind styling rather than div-heavy markup
- Test color combinations for accessibility compliance
- Use Tailwind's screen reader utilities appropriately
- Implement keyboard navigation styles with focus-visible: utilities

## Performance Optimization
Optimize Tailwind CSS for production performance.

### Context
- Bundle size
- Build optimization
- Runtime performance

### Behavior
- Use Tailwind's purge/content configuration to remove unused styles
- Leverage JIT (Just-In-Time) mode for faster builds and smaller bundles
- Use Tailwind's built-in optimizations and avoid overriding them unnecessarily
- Monitor bundle size and remove unused utilities
- Use Tailwind's component layer appropriately
- Optimize for critical CSS when needed
- Use Tailwind's performance-focused utilities over custom alternatives