---
category: "coding"
applies_to: ["claude", "gpt", "generic"]
language: "php"
---

# PHP Coding Standards

## Code Style
Follow PSR-12 extended coding style guide.

### Context
- All PHP files
- Class definitions
- Function declarations

### Behavior
- Use 4 spaces for indentation, never tabs
- Opening braces on same line for control structures
- Opening braces on new line for classes and functions
- Use camelCase for methods and variables
- Use PascalCase for class names
- Use UPPER_CASE for constants

## Accessibility (a11y)
Ensure PHP-generated content supports accessibility.

### Context
- HTML output generation
- Form processing
- Content management
- Template rendering

### Behavior
- Generate semantic HTML with proper structure and heading hierarchy
- Include proper alt attributes for dynamically generated images
- Create accessible forms with labels and error messages
- Implement proper ARIA attributes in dynamic content
- Ensure keyboard navigation works in generated interfaces
- Test generated content with screen readers
- Provide descriptive link text and avoid "click here"
- Support skip navigation and landmark roles in templates

## Security Practices
Implement secure coding patterns.

### Context
- User input handling
- Database queries
- File operations
- Authentication
- Output generation

### Behavior
- Always sanitize and validate input
- Escape output based on context (HTML, JavaScript, SQL, etc.)
- Use prepared statements for database queries
- Never use `eval()` or similar dangerous functions
- Implement proper error handling without exposing system details
- Use password_hash() and password_verify() for passwords
- Validate file uploads and restrict file types
- Use htmlspecialchars() or equivalent for HTML output
- Implement CSRF protection for forms
- Use secure session configuration
- Validate and sanitize file paths to prevent directory traversal
- Implement rate limiting for sensitive operations

## Modern PHP Features
Use contemporary PHP syntax and features.

### Context
- PHP 8.0+ projects
- New code development
- Refactoring legacy code

### Behavior
- Use type declarations for parameters and return types
- Implement constructor property promotion when appropriate
- Use null coalescing operator (??) instead of isset() checks
- Prefer match expressions over switch when suitable
- Use arrow functions for simple callbacks
- Implement readonly properties when data shouldn't change

## Error Handling
Implement robust error handling.

### Context
- Exception handling
- Error reporting
- Logging

### Behavior
- Use try-catch blocks for recoverable errors
- Create custom exception classes when appropriate
- Log errors appropriately without exposing sensitive data
- Use proper HTTP status codes in API responses
- Implement graceful degradation for non-critical failures

## Performance Optimization
Write efficient PHP code for optimal performance.

### Context
- Server performance
- Database optimization
- Memory management
- Caching strategies

### Behavior
- Use opcode caching (OPcache) in production
- Implement efficient database queries with proper indexing
- Use prepared statements for repeated queries
- Implement caching strategies (Redis, Memcached)
- Optimize memory usage and avoid memory leaks
- Use efficient algorithms and data structures
- Profile and monitor application performance
- Minimize file I/O operations and optimize autoloading