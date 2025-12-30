---
name: docs-as-code
description: Master docs-as-code with Git workflows, Markdown, static site generators, and automated publishing pipelines.
---

# Docs-as-Code

Implement docs-as-code workflows using version control, Markdown, and automated publishing for scalable documentation.

## When to Use This Skill

- Developer documentation
- Version-controlled docs
- Collaborative writing
- Automated publishing
- Multi-version docs
- Technical documentation
- API references
- Open source projects

## Core Concepts

### 1. Docs-as-Code Workflow

```
Write (Markdown) → Commit (Git) → Review (PR) → Build (CI) → Deploy (Static Site)
```

### 2. MkDocs Project Structure

```
my-docs/
├── mkdocs.yml          # Configuration
├── docs/
│   ├── index.md        # Home page
│   ├── getting-started.md
│   ├── api/
│   │   ├── overview.md
│   │   └── reference.md
│   └── guides/
│       ├── authentication.md
│       └── deployment.md
└── .github/
    └── workflows/
        └── deploy-docs.yml  # CI/CD
```

### 3. mkdocs.yml Configuration

```yaml
site_name: My Documentation
site_url: https://docs.example.com
theme:
  name: material
  features:
    - navigation.tabs
    - search.highlight
nav:
  - Home: index.md
  - Getting Started: getting-started.md
  - API:
    - Overview: api/overview.md
    - Reference: api/reference.md
  - Guides:
    - Authentication: guides/authentication.md
    - Deployment: guides/deployment.md
plugins:
  - search
  - git-revision-date
markdown_extensions:
  - pymdownx.highlight
  - pymdownx.superfences
  - admonition
```

### 4. GitHub Actions Deployment

```yaml
name: Deploy Docs

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: 3.x
          
      - name: Install dependencies
        run: pip install mkdocs-material
        
      - name: Deploy
        run: mkdocs gh-deploy --force
```

## Best Practices

1. **Use Git** - Version control for all docs
2. **Markdown first** - Simple, portable format
3. **Review process** - Pull requests for changes
4. **Automate builds** - CI/CD pipelines
5. **Test locally** - Preview before publishing
6. **Semantic versioning** - Version your docs
7. **Search enabled** - Make content findable
8. **Link checking** - Validate links regularly

## Resources

- **MkDocs**: https://www.mkdocs.org
- **Docusaurus**: https://docusaurus.io
- **Material for MkDocs**: https://squidfunk.github.io/mkdocs-material/
