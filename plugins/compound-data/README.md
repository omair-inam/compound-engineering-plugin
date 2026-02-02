# Compound Data

Database migrations and data integrity tools for safe data operations.

## Installation

```bash
claude /plugin install compound-data
```

## Agents (3)

| Agent | Description |
|-------|-------------|
| `data-integrity-guardian` | Review database migrations for data integrity risks |
| `data-migration-expert` | Validate ID mappings, check for swapped values |
| `deployment-verification-agent` | Create Go/No-Go deployment checklists |

## Usage Examples

### Review a migration

```bash
claude agent data-integrity-guardian "Review this migration for data loss risks"
```

### Validate data mapping

```bash
claude agent data-migration-expert "Check the ID mappings in this data transfer"
```

### Create deployment checklist

```bash
claude agent deployment-verification-agent "Create a Go/No-Go checklist for this release"
```

## Related Plugins

- **compound-core** - Universal compounding engineering tools
- **compound-design** - UI/Figma design workflow tools

## License

MIT
