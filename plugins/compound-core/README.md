# Compound Core

Universal compounding engineering tools for AI-powered development. 10 agents, 3 commands, and 1 skill focused on code review, research, and workflow automation.

## Philosophy

**Each unit of engineering work should make subsequent units of work easier—not harder.**

This plugin embodies the compounding engineering approach: systematically capturing and reusing knowledge to accelerate future development.

## Installation

```bash
claude /plugin install compound-core
```

## Components

### Agents (10)

#### Review Agents (5)

| Agent | Description |
|-------|-------------|
| `architecture-strategist` | Analyze architectural decisions and compliance |
| `code-simplicity-reviewer` | Final pass for simplicity and minimalism |
| `pattern-recognition-specialist` | Analyze code for patterns and anti-patterns |
| `performance-oracle` | Performance analysis and optimization |
| `security-sentinel` | Security audits and vulnerability assessments |

#### Research Agents (3)

| Agent | Description |
|-------|-------------|
| `best-practices-researcher` | Gather external best practices and examples |
| `framework-docs-researcher` | Research framework documentation |
| `git-history-analyzer` | Analyze git history and code evolution |

#### Workflow Agents (2)

| Agent | Description |
|-------|-------------|
| `bug-reproduction-validator` | Systematically reproduce and validate bugs |
| `spec-flow-analyzer` | Analyze user flows and identify gaps |

### Commands (3)

| Command | Description |
|---------|-------------|
| `/workflows:compound` | Document solved problems to compound team knowledge |
| `/deepen-plan` | Enhance plans with parallel research agents |
| `/changelog` | Create engaging changelogs for recent merges |

### Skills (1)

| Skill | Description |
|-------|-------------|
| `compound-docs` | Capture solved problems as categorized documentation |

## Usage Examples

### Run a code review

```bash
claude agent architecture-strategist "Review this PR for architectural concerns"
```

### Research best practices

```bash
claude agent best-practices-researcher "Find examples of pagination in Rails APIs"
```

### Document a solved problem

```bash
claude /workflows:compound
```

## Related Plugins

- **compound-data** - Database migrations and data integrity tools
- **compound-design** - UI/Figma design workflow tools

## License

MIT
