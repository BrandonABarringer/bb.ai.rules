---
version: "1.0"
category: "coding"
applies_to: ["claude", "gpt", "generic"]
language: "css"
---

# CSS Coding Standards

## Code Organization
Structure CSS for maintainability and scalability.

### Context
- Stylesheet organization
- Component-based styling
- Property and selector ordering

### Behavior
- Use CSS nesting for component-based organization
- Order properties logically: positioning, display, dimensions, colors, typography
- Order selectors by visual hierarchy (parent to child, top to bottom)
- Use consistent indentation (2 spaces)
- One selector per line for multi-selector rules
- Include comments for complex or non-obvious styles

## Modern CSS Features
Use contemporary CSS capabilities.

### Context
- Layout systems
- Responsive design
- Component styling

### Behavior
- Prefer CSS Grid and Flexbox over floats
- Use CSS custom properties (variables) for theming
- Use CSS nesting for component organization
- Use @import for modular CSS organization
- Implement clamp() for responsive typography
- Use logical properties (margin-inline, padding-block)
- Leverage :has() selector when appropriate
- Use container queries for component-based responsive design
- Implement CSS layers (@layer) for cascade management

## Performance Optimization
Write efficient CSS for better performance.

### Context
- Selector efficiency
- File size optimization
- Rendering performance

### Behavior
- Avoid overly specific selectors
- Minimize use of universal selectors (*)
- Use shorthand properties when appropriate
- Optimize critical CSS for above-the-fold content
- Use will-change sparingly and remove after animations
- Minimize reflows and repaints with transform and opacity

## Accessibility (a11y)
Ensure CSS supports accessibility and inclusive design.

### Context
- Screen reader compatibility
- Keyboard navigation
- WCAG compliance
- Visual accessibility

### Behavior
- Maintain sufficient color contrast ratios (4.5:1 for normal text, 3:1 for large text)
- Don't remove focus indicators without providing clear alternatives
- Use relative units (rem, em) for scalable designs
- Ensure content is readable when zoomed to 200%
- Support high contrast and reduced motion preferences
- Avoid using content property for essential information
- Design for keyboard navigation with clear focus states
- Test with screen readers and keyboard-only navigation
- Use logical properties for better internationalization support

## Security
Implement CSS security best practices.

### Context
- Security considerations
- Content Security Policy

### Behavior
- Be cautious with user-generated CSS content
- Use CSP-compatible styles (avoid inline styles when CSP is strict)
- Validate any dynamic CSS generation