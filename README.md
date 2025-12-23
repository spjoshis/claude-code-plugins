# Claude Code Plugins

## Overview

This repository provides a modular collection of plugins to enhance Python development workflows. It is organized to support agent-based expertise and encapsulated skills, making it easy to extend, share, and apply best practices in Python projects.

## Usage

### Add market place
Add the plugin marketplace to your Claude environment using the following command:

```bash
/plugin marketplace add spjoshis/claude-code-plugins
```


### Install plugins
Install the plugin with the command:

```bash
/plugin install python-development@cc-plugins
```

### Available Plugins

- **python-development**: A Claude plugin to assist with Python development tasks including code generation, debugging, testing, and optimization.

### Agents

- **fastapi-expert.md**: Expert guidance and automation for FastAPI development.
- **python-expert.md**: General Python expertise, advanced tips, and best practices.

### Skills

- **async-python-patterns/SKILL.md**: Patterns and best practices for asynchronous programming in Python.
- **python-performance-optimization/SKILL.md**: Strategies and techniques for optimizing Python code performance.
- **uv-package-manager/SKILL.md**: Usage and best practices for the `uv` Python package manager.

## Usage

1. Browse to the relevant agent or skill directory.
2. Read the Markdown documentation for detailed instructions, code examples, and recommendations.
3. Integrate the provided patterns or guidance into your own Python projects.

## Contributing

Contributions are welcome! To add a new agent or skill:

1. Fork the repository and create a new branch.
2. Add your agent Markdown file to `agents/` or create a new skill subfolder under `skills/` with a `SKILL.md` file.
3. Follow the existing documentation style for consistency.
4. Submit a pull request with a clear description of your addition.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
