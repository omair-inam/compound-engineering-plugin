# Compound Plugins

[![Build Status](https://github.com/omair-inam/compound-engineering-plugin/actions/workflows/ci.yml/badge.svg)](https://github.com/omair-inam/compound-engineering-plugin/actions/workflows/ci.yml)

A Claude Code plugin marketplace featuring focused, modular plugins for compounding engineering workflows.

> **Fork Note:** This is a streamlined fork of [EveryInc/compound-engineering-plugin](https://github.com/EveryInc/compound-engineering-plugin). The original monolithic plugin (~67 components, ~22k context tokens) has been split into 3 focused plugins (~21 components, ~5-6k tokens) to reduce context overhead. Language-specific reviewers (Rails, Python, TypeScript), Every.co-specific tools, and components overlapping with the [superpowers plugin](https://github.com/anthropics/claude-code-plugins) were removed. All remaining content has been generalized to be framework-agnostic, replacing Rails/Ruby-specific terminology with multi-ecosystem examples spanning Java/Spring, Python, Angular, and Node.js.

## Installation

```bash
# Add this marketplace
/plugin marketplace add https://github.com/omair-inam/compound-engineering-plugin

# Install the core plugin (recommended for most users)
/plugin install compound-core

# Optional: Install additional plugins as needed
/plugin install compound-data    # Database/migration tools
/plugin install compound-design  # UI/Figma design tools
```

## Available Plugins

| Plugin | Components | Description |
|--------|------------|-------------|
| **compound-core** | 10 agents, 3 commands, 1 skill | Universal compounding engineering tools for code review, research, and workflow automation |
| **compound-data** | 3 agents | Database migrations and data integrity tools |
| **compound-design** | 3 agents, 1 skill | UI/Figma design workflow tools |
| **coding-tutor** | 3 commands, 1 skill | Personalized coding tutorials with spaced repetition |

## Workflow

The core workflow centers on documenting solved problems to compound knowledge:

```
Work → Document → Compound → Repeat
```

| Command | Purpose |
|---------|---------|
| `/workflows:compound` | Document solved problems to compound team knowledge |
| `/deepen-plan` | Enhance plans with parallel research agents |
| `/changelog` | Create engaging changelogs for recent merges |

## Philosophy

**Each unit of engineering work should make subsequent units easier—not harder.**

Traditional development accumulates technical debt. Every feature adds complexity. The codebase becomes harder to work with over time.

Compound engineering inverts this:
- Review to catch issues and capture learnings
- Codify knowledge so it's reusable
- Keep quality high so future changes are easy

## Plugin Details

### compound-core

Universal tools that work across any codebase.

**Review Agents:** architecture-strategist, code-simplicity-reviewer, pattern-recognition-specialist, performance-oracle, security-sentinel

**Research Agents:** best-practices-researcher, framework-docs-researcher, git-history-analyzer

**Workflow Agents:** bug-reproduction-validator, spec-flow-analyzer

**Skill:** compound-docs (capture solved problems as categorized documentation)

[Full reference →](plugins/compound-core/README.md)

### compound-data

Tools for safe database operations.

**Agents:** data-integrity-guardian, data-migration-expert, deployment-verification-agent

[Full reference →](plugins/compound-data/README.md)

### compound-design

Tools for UI/Figma design workflows.

**Agents:** design-implementation-reviewer, design-iterator, figma-design-sync

**Skill:** frontend-design (create production-grade frontend interfaces)

[Full reference →](plugins/compound-design/README.md)

## Learn More

- [Compound engineering: how Every codes with agents](https://every.to/chain-of-thought/compound-engineering-how-every-codes-with-agents)
- [The story behind compounding engineering](https://every.to/source-code/my-ai-had-already-fixed-the-code-before-i-saw-it)
- [Original plugin (upstream)](https://github.com/EveryInc/compound-engineering-plugin)
