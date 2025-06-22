---
version: "1.0"
category: "coding"
applies_to: ["claude", "gpt", "generic"]
language: "html"
---

# HTML Coding Standards

## Semantic HTML
Use proper semantic HTML5 elements for structure and meaning.

### Context
- Document structure
- Content organization
- Screen reader compatibility

### Behavior
- Use semantic elements (header, nav, main, section, article, aside, footer)
- Implement proper heading hierarchy (h1-h6) without skipping levels
- Use appropriate form elements (fieldset, legend, label, input types)
- Choose elements based on meaning, not appearance
- Use lists (ul, ol, dl) for related content groups
- Use table elements only for tabular data
- Avoid generic divs and spans when semantic alternatives exist

## Accessibility (a11y)
Ensure HTML is accessible to all users and assistive technologies.

### Context
- Screen reader compatibility
- Keyboard navigation
- WCAG compliance

### Behavior
- Provide descriptive alt text for all images
- Use proper form labels and associate them with inputs
- Implement ARIA attributes when semantic HTML is insufficient
- Ensure sufficient color contrast and don't rely solely on color
- Provide skip navigation links for keyboard users
- Use descriptive link text (avoid "click here")
- Implement proper focus management and visible focus indicators
- Use landmark roles and proper heading structure
- Provide captions and transcripts for multimedia content
- Test with screen readers and keyboard-only navigation

## Code Quality
Write clean, maintainable HTML code.

### Context
- Code organization
- Validation
- Performance
- Formatting consistency

### Behavior
- Use consistent indentation (2 spaces)
- Write lowercase element names and attributes
- Quote all attribute values
- Close all tags properly
- When multiple attributes are used, place each attribute on its own line
- Place content within tags on their own lines regardless of block or inline elements
- Validate HTML using W3C validator
- Use meaningful class and ID names
- Avoid inline styles and JavaScript
- Minimize nested elements when possible
- Use comments to explain complex structures

## Performance Optimization
Optimize HTML for fast loading and rendering.

### Context
- Page load speed
- Core Web Vitals
- SEO optimization
- User experience

### Behavior
- Optimize images with proper formats and sizes
- Use lazy loading for images below the fold
- Implement proper meta tags for SEO and social sharing
- Use semantic markup to improve SEO and parsing
- Avoid excessive DOM depth and nesting
- Minimize HTTP requests through efficient markup
- Use proper encoding (UTF-8) and DOCTYPE declaration
- Preload critical resources and fonts
- Use resource hints (preconnect, prefetch) appropriately

## Security
Implement HTML security best practices.

### Context
- Content security
- XSS prevention
- Data validation

### Behavior
- Sanitize any user-generated content
- Implement Content Security Policy compatible markup
- Use proper form validation attributes
- Avoid inline scripts and styles when possible