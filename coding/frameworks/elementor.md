---
version: "1.0"
category: "coding"
applies_to: ["claude", "gpt", "generic"]
framework: "elementor"
---

# Elementor Framework Standards

## Widget Development
Follow Elementor widget development best practices.

### Context
- Custom widget creation
- Widget controls and settings
- Widget rendering

### Behavior
- Extend \Elementor\Widget_Base for all custom widgets
- Use proper control types (text, textarea, select, etc.)
- Implement get_name(), get_title(), get_icon(), and get_categories()
- Use render() method for frontend output
- Register widgets properly with Plugin::instance()->widgets_manager->register()
- Use Elementor's responsive controls when appropriate

## Component Architecture with Elementor
Follow specific patterns for WordPress + Elementor component development.

### Context
- Elementor widgets requiring JavaScript functionality
- Component reusability
- Non-Elementor page compatibility

### Behavior
- Create custom web components with TypeScript for functionality
- Build PHP partials outside Elementor widgets using get_template_part()
- Use Elementor data to populate reusable PHP partials
- Create dedicated component folders containing all related files
- Include component-specific CSS and TypeScript within component folders
- Add README.md files to component folders documenting usage and Elementor integration
- Design components to be self-contained and data-driven
- Make components container-agnostic but responsive to container size
- Plan component layouts to adapt based on available container space
- Ensure components work in both Elementor and traditional WordPress contexts

## Custom Controls
Create and implement custom controls properly.

### Context
- Advanced widget settings
- Custom input types
- Control groups

### Behavior
- Extend \Elementor\Base_Data_Control for custom controls
- Implement get_type() and enqueue() methods
- Use proper control dependencies and conditions
- Implement proper sanitization for custom control values
- Register controls with Plugin::instance()->controls_manager->register()
- Use control groups for related settings

## Performance and Security
Optimize Elementor implementations for performance and security.

### Context
- Database queries
- User input handling
- Component rendering

### Behavior
- Use Elementor's asset optimization features
- Implement proper capability checks for admin features
- Sanitize all user inputs in widget controls
- Use Elementor's caching mechanisms appropriately
- Design components to be container-agnostic for flexible layouts
- Use Elementor's responsive breakpoint system efficiently

## Accessibility (a11y)
Ensure Elementor widgets and components are accessible.

### Context
- Widget development
- Content output
- User interactions
- Screen reader compatibility

### Behavior
- Use semantic HTML elements in widget render() methods
- Implement proper ARIA attributes and roles in widgets
- Ensure keyboard navigation works for all interactive elements
- Provide proper focus management in custom controls
- Use accessible color contrasts and don't rely solely on color for information
- Test widgets with screen readers and keyboard-only navigation
- Implement proper heading hierarchy in widget content
- Provide alternative text for images and icons
- Make custom controls accessible with proper labels
- Ensure widgets work properly with WordPress accessibility features