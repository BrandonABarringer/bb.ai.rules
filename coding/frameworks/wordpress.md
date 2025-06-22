---
category: "coding"
applies_to: ["claude", "gpt", "generic"]
framework: "wordpress"
---

# WordPress Framework Standards

## WordPress Coding Standards
Follow WordPress-specific conventions and best practices.

### Context
- Theme development
- Plugin development
- Custom functionality

### Behavior
- Follow WordPress PHP Coding Standards
- Use WordPress naming conventions (underscores for functions/variables)
- Prefix all custom functions, classes, and globals
- Use WordPress hooks (actions and filters) instead of modifying core
- Follow WordPress file structure conventions
- Use WordPress coding standards for HTML, CSS, and TypeScript

## Component Architecture
Organize reusable components using WordPress partials.

### Context
- Reusable UI components
- Template organization
- Component-based development

### Behavior
- Use get_template_part() for rendering reusable PHP partials
- Build partials to accept data passed via get_template_part()
- Create dedicated component folders containing all related files
- Include component-specific CSS and TypeScript within component folders
- Add README.md files to component folders documenting usage and props
- Design components to be self-contained and data-driven
- Make components container-agnostic but responsive to container size
- Plan component layouts to adapt based on available container space
- Use consistent naming conventions for component organization

## Security Practices
Implement WordPress-specific security measures.

### Context
- User input handling
- Database operations
- File uploads
- Authentication

### Behavior
- Always sanitize input using WordPress functions (sanitize_text_field, etc.)
- Escape output using WordPress functions (esc_html, esc_attr, esc_url)
- Use WordPress nonces for form security
- Validate and sanitize all $_POST, $_GET, and $_REQUEST data
- Use wp_safe_redirect() instead of wp_redirect() when possible
- Implement proper capability checks with current_user_can()
- Use wpdb->prepare() for all database queries
- Validate file uploads and restrict file types

## Database Operations
Use WordPress database API properly.

### Context
- Custom queries
- Data retrieval
- Data manipulation

### Behavior
- Use WP_Query, get_posts(), or WP_User_Query instead of direct SQL when possible
- Always use $wpdb->prepare() for custom queries
- Use WordPress caching functions (wp_cache_set, wp_cache_get)
- Implement proper error handling for database operations
- Use WordPress transients for temporary data storage
- Follow WordPress database schema conventions for custom tables

## Performance Optimization
Optimize WordPress-specific performance concerns.

### Context
- Query optimization
- Asset loading
- Caching strategies

### Behavior
- Use WP_Query arguments efficiently (avoid query_posts())
- Implement proper asset enqueueing with wp_enqueue_script/style
- Use conditional loading for admin-only or frontend-only assets
- Implement object caching where appropriate
- Optimize images and use WordPress image sizes
- Use WordPress lazy loading features
- Minimize plugin conflicts by checking for function/class existence

## Accessibility (a11y)
Ensure WordPress sites are accessible to all users.

### Context
- Theme development
- Content output
- Form handling
- Navigation

### Behavior
- Use semantic HTML5 elements and proper heading hierarchy
- Implement proper ARIA labels and roles where needed
- Ensure keyboard navigation works throughout the site
- Use WordPress accessibility-ready theme standards
- Provide alternative text for images using WordPress media functions
- Implement proper focus management and skip links
- Use WordPress built-in accessibility features and functions
- Test with screen readers and accessibility tools
- Ensure sufficient color contrast ratios in themes
- Make forms accessible with proper labels and error messages