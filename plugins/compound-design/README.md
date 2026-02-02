# Compound Design

UI/Figma design workflow tools for implementing and iterating on designs.

## Installation

```bash
claude /plugin install compound-design
```

## Agents (3)

| Agent | Description |
|-------|-------------|
| `design-implementation-reviewer` | Verify UI implementation matches Figma designs |
| `design-iterator` | Iteratively refine UI through systematic iterations |
| `figma-design-sync` | Synchronize web implementations with Figma designs |

## Skills (1)

| Skill | Description |
|-------|-------------|
| `frontend-design` | Create distinctive, production-grade frontend interfaces |

## Usage Examples

### Review design implementation

```bash
claude agent design-implementation-reviewer "Compare the header component to the Figma design"
```

### Iterate on a design

```bash
claude agent design-iterator "Refine the card component layout"
```

### Sync with Figma

```bash
claude agent figma-design-sync "Update the button styles to match Figma"
```

### Create a frontend component

```bash
claude skill frontend-design
```

## Related Plugins

- **compound-core** - Universal compounding engineering tools
- **compound-data** - Database migrations and data integrity tools

## License

MIT
