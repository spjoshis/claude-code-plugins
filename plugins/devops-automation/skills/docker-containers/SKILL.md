---
name: docker-containers
description: Master Docker with containers, images, multi-stage builds, Docker Compose, networking, and production-ready containerization.
---

# Docker Containerization

Build and deploy applications with Docker containers, multi-stage builds, and production-ready configurations.

## Core Patterns

### Dockerfile
```dockerfile
# Multi-stage build
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM node:20-alpine
WORKDIR /app
COPY --from=builder /app/dist ./dist
COPY package*.json ./
RUN npm ci --production
EXPOSE 3000
CMD ["node", "dist/index.js"]
```

### Docker Compose
```yaml
version: '3.8'

services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - DATABASE_URL=postgres://user:pass@db:5432/myapp
    depends_on:
      - db
      - redis

  db:
    image: postgres:16-alpine
    environment:
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=pass
      - POSTGRES_DB=myapp
    volumes:
      - postgres_data:/var/lib/postgresql/data

  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

volumes:
  postgres_data:
```

### Build and Run
```bash
# Build image
docker build -t myapp:latest .

# Run container
docker run -d -p 3000:3000 --name myapp myapp:latest

# View logs
docker logs -f myapp

# Execute command in container
docker exec -it myapp sh
```

## Best Practices

1. Use multi-stage builds
2. Minimize layer count
3. Use .dockerignore
4. Run as non-root user
5. Use alpine images
6. Implement health checks
7. Use Docker secrets
8. Tag images properly

## Resources
- https://docs.docker.com
