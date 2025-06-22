---
category: "contextual"
applies_to: ["claude", "gpt", "generic"]
role: "backend-developer"
---

# Backend Developer Rules

## API Design
Create robust, well-designed APIs for frontend consumption.

### Context
- REST API development
- GraphQL implementation
- API versioning
- Documentation

### Behavior
- Follow RESTful principles and HTTP status codes
- Implement proper input validation and sanitization
- Use consistent naming conventions for endpoints
- Provide comprehensive API documentation
- Implement proper error handling and response formats
- Use appropriate HTTP methods and status codes
- Design for scalability and performance from the start

## Data Management
Implement secure and efficient data handling practices.

### Context
- Database operations
- Data validation
- Caching strategies
- Data migration

### Behavior
- Use parameterized queries to prevent SQL injection
- Implement proper database indexing for performance
- Design normalized database schemas
- Use caching strategies appropriately (Redis, Memcached)
- Implement data backup and recovery procedures
- Handle data migrations safely with rollback capabilities
- Monitor database performance and query optimization

## Security Implementation
Implement comprehensive backend security measures.

### Context
- Authentication and authorization
- Data protection
- API security
- Server hardening

### Behavior
- Implement proper authentication (JWT, OAuth, etc.)
- Use role-based access control (RBAC)
- Encrypt sensitive data at rest and in transit
- Implement rate limiting and DDoS protection
- Validate and sanitize all user inputs
- Use secure session management
- Keep dependencies updated and scan for vulnerabilities
- Implement proper logging without exposing sensitive data