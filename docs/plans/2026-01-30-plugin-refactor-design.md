# Plugin Refactor Design

**Date:** 2026-01-30
**Goal:** Reduce context overhead from ~22k tokens to ~5-6k tokens by splitting the monolithic compound-engineering plugin into focused, modular plugins.

## Overview

Create three separate plugins in a monorepo structure:

1. **compound-core** - Universal compounding engineering tools
2. **compound-data** - Database migrations and data integrity
3. **compound-design** - UI/Figma workflows

## Repository Structure

```
compound-plugins/
├── plugins/
│   ├── compound-core/
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── agents/
│   │   │   ├── review/
│   │   │   │   ├── architecture-strategist.md
│   │   │   │   ├── code-simplicity-reviewer.md
│   │   │   │   ├── pattern-recognition-specialist.md
│   │   │   │   ├── performance-oracle.md
│   │   │   │   └── security-sentinel.md
│   │   │   ├── research/
│   │   │   │   ├── best-practices-researcher.md
│   │   │   │   ├── framework-docs-researcher.md
│   │   │   │   └── git-history-analyzer.md
│   │   │   └── workflow/
│   │   │       ├── bug-reproduction-validator.md
│   │   │       └── spec-flow-analyzer.md
│   │   ├── commands/
│   │   │   ├── changelog.md
│   │   │   ├── deepen-plan.md
│   │   │   └── workflows/
│   │   │       └── compound.md
│   │   ├── skills/
│   │   │   └── compound-docs/
│   │   │       └── SKILL.md
│   │   ├── README.md
│   │   └── CHANGELOG.md
│   │
│   ├── compound-data/
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── agents/
│   │   │   ├── data-integrity-guardian.md
│   │   │   ├── data-migration-expert.md
│   │   │   └── deployment-verification-agent.md
│   │   └── README.md
│   │
│   └── compound-design/
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── agents/
│       │   ├── design-implementation-reviewer.md
│       │   ├── design-iterator.md
│       │   └── figma-design-sync.md
│       ├── skills/
│       │   └── frontend-design/
│       │       └── SKILL.md
│       └── README.md
│
├── .claude-plugin/
│   └── marketplace.json      # Lists all 3 plugins
└── README.md
```

## Plugin Details

### compound-core

The main plugin focused on the "compounding engineering" philosophy.

**Agents (10):**

| Category | Agent | Description |
|----------|-------|-------------|
| Review | architecture-strategist | Analyze architectural decisions and compliance |
| Review | code-simplicity-reviewer | Final pass for simplicity and minimalism |
| Review | pattern-recognition-specialist | Analyze code for patterns and anti-patterns |
| Review | performance-oracle | Performance analysis and optimization |
| Review | security-sentinel | Security audits and vulnerability assessments |
| Research | best-practices-researcher | Gather external best practices and examples |
| Research | framework-docs-researcher | Research framework documentation |
| Research | git-history-analyzer | Analyze git history and code evolution |
| Workflow | bug-reproduction-validator | Systematically reproduce and validate bugs |
| Workflow | spec-flow-analyzer | Analyze user flows and identify gaps |

**Commands (3):**

| Command | Description |
|---------|-------------|
| workflows:compound | Document solved problems to compound team knowledge |
| deepen-plan | Enhance plans with parallel research agents |
| changelog | Create engaging changelogs for recent merges |

**Skills (1):**

| Skill | Description |
|-------|-------------|
| compound-docs | Capture solved problems as categorized documentation |

### compound-data

Optional plugin for database and data migration workflows.

**Agents (3):**

| Agent | Description |
|-------|-------------|
| data-integrity-guardian | Database migrations and data integrity |
| data-migration-expert | Validate ID mappings, check for swapped values |
| deployment-verification-agent | Create Go/No-Go deployment checklists |

### compound-design

Optional plugin for UI/Figma design workflows.

**Agents (3):**

| Agent | Description |
|-------|-------------|
| design-implementation-reviewer | Verify UI matches Figma designs |
| design-iterator | Iteratively refine UI through systematic iterations |
| figma-design-sync | Synchronize web implementations with Figma |

**Skills (1):**

| Skill | Description |
|-------|-------------|
| frontend-design | Create distinctive, production-grade frontend interfaces |

## Discarded Components

The following are NOT migrated to the new plugins:

### Language/Framework Specific
- dhh-rails-reviewer (Rails)
- kieran-rails-reviewer (Rails)
- kieran-python-reviewer (Python)
- kieran-typescript-reviewer (TypeScript)
- dhh-rails-style skill (Rails)
- andrew-kane-gem-writer skill (Ruby)
- ankane-readme-writer agent (Ruby)
- lint agent (Ruby/ERB)
- dspy-ruby skill (Ruby)

### Every.co Specific
- every-style-editor agent + skill
- learnings-researcher agent

### Tool Specific
- gemini-imagegen skill
- agent-browser skill
- xcode-test command
- rclone skill

### Overlaps with Superpowers Plugin
- brainstorming skill (superpowers has this)
- git-worktree skill (superpowers has using-git-worktrees)
- file-todos skill (superpowers has task tracking)
- create-agent-skills command (superpowers has writing-skills)
- heal-skill command
- generate_command command

### Agent-Native (removed as a category)
- agent-native-reviewer agent
- agent-native-architecture skill
- agent-native-audit command

### Other Discarded Commands
- workflows:plan (superpowers has /write-plan)
- workflows:review (superpowers has code-reviewer)
- workflows:work (superpowers has /execute-plan)
- plan_review (Every-specific reviewers)
- lfg (Every-specific workflow)
- resolve_* commands (Every-specific todo system)
- report-bug / reproduce-bug (plugin maintenance)
- triage (Every-specific)
- test-browser (tool-specific)
- feature-video (tool-specific)
- release-docs / deploy-docs (Every's docs site)

### MCP Servers
- context7 (users can add manually: `https://mcp.context7.com/mcp`)

## Expected Results

| Metric | Before | After (core only) |
|--------|--------|-------------------|
| Context tokens | ~22k | ~5-6k |
| Agents | 27 | 10 |
| Commands | 20 | 3 |
| Skills | 14 | 1 |
| MCP Servers | 1 | 0 |

## Implementation Notes

1. Create new monorepo structure
2. Copy relevant agents/commands/skills from source
3. Update plugin.json for each plugin
4. Create marketplace.json listing all plugins
5. Write README for each plugin
6. Test installation of each plugin individually
