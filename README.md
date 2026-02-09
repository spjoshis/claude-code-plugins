# Claude Code Plugins

## Overview

This repository provides a comprehensive collection of plugins to enhance software development and project management workflows. It includes specialized plugins for various programming languages, frameworks, and professional roles, making it easy to extend Claude's capabilities with domain-specific expertise and best practices.


## Usage

### Add Marketplace
Add the plugin marketplace to your Claude environment using the following command:

```bash
/plugin marketplace add spjoshis/claude-code-plugins
```

### Install Plugins
Install any plugin with the command:

```bash
/plugin install <plugin-name>@cc-plugins
```

For example:
```bash
/plugin install python-development@cc-plugins
/plugin install react-development@cc-plugins
/plugin install solutions-architect@cc-plugins
```

## Available Plugins

### Development Languages & Frameworks

#### **angular-development**
Angular web application development with TypeScript.
- **Agents**: angular-expert.md
- **Skills**: angular-performance, angular-services, ngrx-state, rxjs-patterns

#### **dotnet-development**
.NET and C# development for enterprise applications.
- **Agents**: dotnet-expert.md
- **Skills**: aspnet-core, blazor-development, csharp-patterns, entity-framework

#### **elixir-development**
Elixir and Phoenix framework for scalable applications.
- **Agents**: elixir-expert.md
- **Skills**: ecto-database, elixir-testing, otp-patterns, phoenix-framework

#### **flutter-development**
Cross-platform mobile development with Flutter and Dart.
- **Agents**: dart-expert.md, flutter-expert.md
- **Skills**: bloc-pattern, flutter-animations, flutter-performance, flutter-state-management

#### **go-development**
Go language development for high-performance systems.
- **Agents**: go-expert.md
- **Skills**: gin-framework, go-concurrency, go-testing, grpc-go

#### **java-development**
Java development for enterprise applications.
- **Agents**: java-expert.md
- **Skills**: java-streams, maven-gradle, microservices-java, spring-boot

#### **kotlin-development**
Kotlin for Android and multiplatform development.
- **Agents**: kotlin-expert.md
- **Skills**: coroutines-kotlin, kotlin-android, kotlin-multiplatform, ktor-framework

#### **nodejs-development**
Node.js and TypeScript backend development.
- **Agents**: nodejs-expert.md
- **Skills**: express-api-development, nestjs-patterns, nodejs-performance, typescript-nodejs

#### **php-development**
PHP development with modern frameworks.
- **Agents**: php-expert.md
- **Skills**: composer-packages, laravel-development, php-testing, symfony-framework

#### **python-development**
Python development with modern tools and frameworks.
- **Agents**: fastapi-expert.md, python-expert.md
- **Skills**: async-python-patterns, python-performance-optimization, uv-package-manager

#### **react-development**
React and Next.js frontend development.
- **Agents**: react-expert.md
- **Skills**: nextjs-development, react-hooks-patterns, react-performance, state-management-react

#### **ruby-development**
Ruby and Rails web development.
- **Agents**: ruby-expert.md
- **Skills**: active-record, rails-patterns, rspec-testing, ruby-gems

#### **rust-development**
Rust systems programming and performance-critical applications.
- **Agents**: rust-expert.md
- **Skills**: async-rust, cargo-workspace, rust-ownership, rust-performance

#### **swift-development**
Swift and iOS application development.
- **Agents**: swift-expert.md
- **Skills**: combine-framework, ios-architecture, swift-concurrency, swiftui-patterns

#### **vue-development**
Vue.js and Nuxt.js frontend development.
- **Agents**: vue-expert.md
- **Skills**: nuxt-development, vue-composition-api, vue-performance, vuex-pinia

### DevOps & Infrastructure

#### **devops-automation**
DevOps practices, CI/CD, and infrastructure automation.
- **Agents**: devops-expert.md
- **Skills**: cicd-pipelines, docker-containers, kubernetes-orchestration, terraform-iac

### Architecture & Design

#### **solutions-architect**
System architecture and design patterns.
- **Agents**: cloud-architect-expert.md, solutions-architect-expert.md
- **Skills**: architecture-documentation, cloud-architecture, scalability-patterns, system-design

#### **ux-designer**
User experience and interface design.
- **Agents**: ui-designer-expert.md, ux-designer-expert.md
- **Skills**: prototyping, usability-testing, user-research, wireframing

### Project Management & Leadership

#### **business-analyst**
Business analysis and requirements engineering.
- **Agents**: business-analyst-expert.md, requirements-engineer.md
- **Skills**: business-documentation, process-modeling, requirements-gathering, use-case-development

#### **product-owner-management**
Product ownership and backlog management.
- **Agents**: product-owner-expert.md, product-strategy-expert.md
- **Skills**: product-backlog-management, product-roadmapping, stakeholder-communication, user-story-writing

#### **project-manager**
Project planning and team coordination.
- **Agents**: agile-pm-expert.md, project-manager-expert.md
- **Skills**: project-planning, project-reporting, risk-management, team-coordination

#### **scrum-master**
Scrum facilitation and agile coaching.
- **Agents**: agile-coach.md, scrum-master-expert.md
- **Skills**: agile-metrics, daily-standups, retrospectives, sprint-planning

### Quality & Security

#### **qa-engineer**
Quality assurance and testing.
- **Agents**: qa-engineer-expert.md, test-automation-expert.md
- **Skills**: manual-testing, performance-testing, test-automation, test-planning

#### **security-analyst**
Security assessment and compliance.
- **Agents**: appsec-expert.md, security-analyst-expert.md
- **Skills**: compliance-management, security-assessment, security-documentation, threat-modeling

### Data & Analytics

#### **data-analyst**
Data analysis and business intelligence.
- **Agents**: business-intelligence-expert.md, data-analyst-expert.md
- **Skills**: data-visualization, excel-analysis, sql-analysis, statistical-analysis

### Documentation

#### **technical-writer**
Technical documentation and content strategy.
- **Agents**: documentation-architect.md, technical-writer-expert.md
- **Skills**: api-documentation, docs-as-code, style-guide-development, user-guide-writing

## Plugin Categories Quick Reference

| Category | Plugins |
|----------|---------|
| **Frontend** | angular-development, react-development, vue-development |
| **Backend** | dotnet-development, elixir-development, go-development, java-development, kotlin-development, nodejs-development, php-development, python-development, ruby-development, rust-development |
| **Mobile** | flutter-development, kotlin-development, swift-development |
| **Infrastructure** | devops-automation |
| **Architecture** | solutions-architect, ux-designer |
| **Management** | business-analyst, product-owner-management, project-manager, scrum-master |
| **Quality** | qa-engineer, security-analyst |
| **Data** | data-analyst |
| **Documentation** | technical-writer |

## Contributing

Contributions are welcome! To add a new agent or skill:

1. Fork the repository and create a new branch.
2. Navigate to the appropriate plugin directory under `plugins/`.
3. Add your agent Markdown file to the `agents/` directory or create a new skill subfolder under `skills/` with a `SKILL.md` file.
4. Follow the existing documentation style and structure for consistency.
5. Submit a pull request with a clear description of your addition.

To create a new plugin:
1. Create a new directory under `plugins/` with your plugin name.
2. Add `agents/` and `skills/` subdirectories.
3. Include relevant expert agents and skills following existing patterns.
4. Update this README.md with your plugin details.

