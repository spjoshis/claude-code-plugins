---
name: api-documentation
description: Master API documentation with REST references, OpenAPI specs, code examples, and developer-friendly API guides.
---

# API Documentation

Create comprehensive API documentation with clear references, code examples, and developer guides for easy integration.

## When to Use This Skill

- Documenting REST APIs
- Creating API references
- Writing integration guides
- Providing code examples
- Documenting authentication
- Explaining error codes
- Rate limiting documentation
- SDK documentation

## Core Concepts

### 1. API Reference Structure

```markdown
## GET /users/{id}

Retrieve a user by ID.

### Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| id | string | Yes | User ID |

### Request Example

```bash
curl -X GET https://api.example.com/users/123 \
  -H "Authorization: Bearer YOUR_TOKEN"
```

### Response Example (200 OK)

```json
{
  "id": "123",
  "name": "John Doe",
  "email": "john@example.com",
  "created_at": "2024-01-01T00:00:00Z"
}
```

### Error Responses

| Code | Description |
|------|-------------|
| 401 | Unauthorized - Invalid token |
| 404 | User not found |
| 429 | Rate limit exceeded |
```

### 2. OpenAPI Specification

```yaml
openapi: 3.0.0
info:
  title: User API
  version: 1.0.0
paths:
  /users/{id}:
    get:
      summary: Get user by ID
      parameters:
        - name: id
          in: path
          required: true
          schema:
            type: string
      responses:
        '200':
          description: Successful response
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/User'
components:
  schemas:
    User:
      type: object
      properties:
        id:
          type: string
        name:
          type: string
        email:
          type: string
```

## Best Practices

1. **Clear examples** - Show request and response
2. **Complete references** - All parameters documented
3. **Error codes** - Document all possible errors
4. **Code samples** - Multiple languages
5. **Authentication** - Clear auth instructions
6. **Rate limits** - Document limits and headers
7. **Versioning** - Version strategy documented
8. **Try it out** - Interactive API explorer

## Resources

- **OpenAPI Specification**: https://swagger.io/specification/
- **Postman Documentation**: Generate docs from collections
